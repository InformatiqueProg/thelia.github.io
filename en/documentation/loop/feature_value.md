---
layout: loop
title: Feature value Loop
description: Feature value loop lists feature availabilities.
sidebar: loop
lang: en
subnav: loop_feature_value
uses_global_argument: true
returns_global_outputs: { countable : true, timestampable : true, versionable : false }
type: feature_value
arguments :
    - {name: "feature", description: "A single feature id.", example: "feature=\"2\"", mandatory: "true"}
    - {name: "product", description: "A single product id. (no longer mandatory since 2.2)", example: "product=\"9\""}
    - {name: "feature_availability", description: "A single or a list of feature availability ids.", example: "feature_availability=\"2,5\""}
    - {name: "free_text", description: "A single or a list of strings. (2.2)", example: "free_text=\"some text,some other text\""}
    - {name: "exclude_feature_availability", description: "A boolean value to return only features with feature availability (no personal value).", example: "feature_availability=\"true\""}
    - {name: "exclude_free_text", description: "A boolean value to return only features with free text value (no feature availability).", example: "exclude_free_text=\"1\" or exclude_free_text=\"true\""}
    - {
            name: "order", description: "A list of values", example: "order=\"alpha_reverse\"", default: "manual",
            expected_values: [
                {name: "alpha",             description: "alphabetical order on title"},
                {name: "alpha_reverse",     description: "reverse alphabetical order on title"},
                {name: "manual",            description: ""},
                {name: "manual_reverse",    description: ""}
            ]
          }

outputs :
    - {name: "$ID", description: "the feature value id"}
    - {name: "$PRODUCT", description: "the id of the product. Deprecated, please use $PRODUCT_ID instead"}
    - {name: "$PRODUCT_ID", description: "(2.2) the id of the product"}
    - {name: "$FEATURE_AV_ID", description: "the feature av. ID. Null if the feature ha no feature av. Use FREE_TEXT_VALUE in this case."}
    - {name: "$IS_FREE_TEXT", description: "1 if this feature is free text, 0 otherwise."}
    - {name: "$IS_FEATURE_AV", description: "1 if this feature is feature av., 0 otherwise."}
    - {name: "$FREE_TEXT_VALUE", description: "1 if this feature is free text, 0 otherwise. Deprecated in 2.4"}
    - {name: "$LOCALE", description: "the locale of returned results"}
    - {name: "$TITLE", description: "the feature availability title, or the feature value text for free text features."}
    - {name: "$CHAPO", description: "the feature availability chapo"}
    - {name: "$DESCRIPTION", description: "the feature availability description"}
    - {name: "$POSTSCRIPTUM", description: "the feature availability postscriptum"}
    - {name: "$POSITION", description: "the feature value position"}
---