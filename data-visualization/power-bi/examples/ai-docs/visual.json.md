# Version 1

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/report/definition/visualContainer/2.5.0/schema.json",
  "name": "ed733890a646ec881fb2",
  "position": {
    "x": 111.24744376278119,
    "y": 123.02658486707567,
    "z": 1000,
    "height": 348.13905930470349,
    "width": 999.918200408998,
    "tabOrder": 0
  },
  "visual": {
    "visualType": "tableEx",
    "query": {
      "queryState": {
        "Values": {
          "projections": [
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Quality Index"
                }
              },
              "queryRef": "prod_data.Quality Index",
              "nativeQueryRef": "Quality Index"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple1"
                }
              },
              "queryRef": "prod_data.Apple 1",
              "nativeQueryRef": "Apple1"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple2"
                }
              },
              "queryRef": "prod_data.Apple2",
              "nativeQueryRef": "Apple2"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple3"
                }
              },
              "queryRef": "prod_data.Apple3",
              "nativeQueryRef": "Apple3"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple4"
                }
              },
              "queryRef": "prod_data.Apple4",
              "nativeQueryRef": "Apple4"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple5"
                }
              },
              "queryRef": "prod_data.Apple5",
              "nativeQueryRef": "Apple5"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple6"
                }
              },
              "queryRef": "prod_data.Apple6",
              "nativeQueryRef": "Apple6"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple7"
                }
              },
              "queryRef": "prod_data.Apple7",
              "nativeQueryRef": "Apple7"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Percentage"
                }
              },
              "queryRef": "Sum(prod_data.Percentage)",
              "nativeQueryRef": "Percentage"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Date Update"
                }
              },
              "queryRef": "prod_data.Date Update",
              "nativeQueryRef": "Date Update"
            }
          ],
          "showAll": true
        }
      },
      "sortDefinition": {
        "sort": [
          {
            "field": {
              "Column": {
                "Expression": {
                  "SourceRef": {
                    "Entity": "prod_data"
                  }
                },
                "Property": "Quality Index"
              }
            },
            "direction": "Ascending"
          }
        ]
      }
    },
    "objects": {
      "columnWidth": [
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple7"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple6"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Quality Index"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple 1"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple2"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple3"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple4"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple5"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "Sum(prod_data.Percentage)"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Date Update"
          }
        }
      ],
      "columnFormatting": [
        {
          "properties": {
            "styleHeader": {
              "expr": {
                "Literal": {
                  "Value": "false"
                }
              }
            },
            "styleTotal": {
              "expr": {
                "Literal": {
                  "Value": "false"
                }
              }
            },
            "styleValues": {
              "expr": {
                "Literal": {
                  "Value": "true"
                }
              }
            }
          },
          "selector": {
            "metadata": "prod_data.Quality Index"
          }
        }
      ],
      "columnHeaders": [
        {
          "properties": {
            "autoSizeColumnWidth": {
              "expr": {
                "Literal": {
                  "Value": "true"
                }
              }
            }
          }
        }
      ],
      "values": [
        {
          "properties": {}
        },
        {
          "properties": {
            "backColor": {
              "solid": {
                "color": {
                  "expr": {
                    "Conditional": {
                      "Cases": [
                        {
                          "Condition": {
                            "Comparison": {
                              "ComparisonKind": 0,
                              "Left": {
                                "Aggregation": {
                                  "Expression": {
                                    "Column": {
                                      "Expression": {
                                        "SourceRef": {
                                          "Entity": "prod_data"
                                        }
                                      },
                                      "Property": "Apple1"
                                    }
                                  },
                                  "Function": 3
                                }
                              },
                              "Right": {
                                "Literal": {
                                  "Value": "'Passed'"
                                }
                              }
                            },
                            "Annotations": {
                              "PowerBI.SQExprEvaluationKind": 1,
                              "PowerBI.SQExprTextOperatorOption": 2
                            }
                          },
                          "Value": {
                            "Literal": {
                              "Value": "'#2DD74B'"
                            }
                          }
                        },
                        {
                          "Condition": {
                            "Comparison": {
                              "ComparisonKind": 0,
                              "Left": {
                                "Aggregation": {
                                  "Expression": {
                                    "Column": {
                                      "Expression": {
                                        "SourceRef": {
                                          "Entity": "prod_data"
                                        }
                                      },
                                      "Property": "Apple1"
                                    }
                                  },
                                  "Function": 3
                                }
                              },
                              "Right": {
                                "Literal": {
                                  "Value": "'Not Passed'"
                                }
                              }
                            },
                            "Annotations": {
                              "PowerBI.SQExprEvaluationKind": 1,
                              "PowerBI.SQExprTextOperatorOption": 2
                            }
                          },
                          "Value": {
                            "Literal": {
                              "Value": "'#eb895f'"
                            }
                          }
                        },
                        {
                          "Condition": {
                            "Comparison": {
                              "ComparisonKind": 0,
                              "Left": {
                                "Aggregation": {
                                  "Expression": {
                                    "Column": {
                                      "Expression": {
                                        "SourceRef": {
                                          "Entity": "prod_data"
                                        }
                                      },
                                      "Property": "Apple1"
                                    }
                                  },
                                  "Function": 3
                                }
                              },
                              "Right": {
                                "Literal": {
                                  "Value": "'N/A'"
                                }
                              }
                            },
                            "Annotations": {
                              "PowerBI.SQExprEvaluationKind": 1,
                              "PowerBI.SQExprTextOperatorOption": 2
                            }
                          },
                          "Value": {
                            "Literal": {
                              "Value": "'#cccccc'"
                            }
                          }
                        },
                        {
                          "Condition": {
                            "Comparison": {
                              "ComparisonKind": 0,
                              "Left": {
                                "Aggregation": {
                                  "Expression": {
                                    "Column": {
                                      "Expression": {
                                        "SourceRef": {
                                          "Entity": "prod_data"
                                        }
                                      },
                                      "Property": "Apple1"
                                    }
                                  },
                                  "Function": 3
                                }
                              },
                              "Right": {
                                "Literal": {
                                  "Value": "''"
                                }
                              }
                            },
                            "Annotations": {
                              "PowerBI.SQExprEvaluationKind": 1,
                              "PowerBI.SQExprTextOperatorOption": 11
                            }
                          },
                          "Value": {
                            "Literal": {
                              "Value": "'#e6e6e6'"
                            }
                          }
                        }
                      ]
                    }
                  }
                }
              }
            }
          },
          "selector": {
            "data": [
              {
                "dataViewWildcard": {
                  "matchingOption": 1
                }
              }
            ],
            "metadata": "prod_data.Apple 1"
          }
        }
      ]
    },
    "visualContainerObjects": {
      "stylePreset": [
        {
          "properties": {
            "name": {
              "expr": {
                "Literal": {
                  "Value": "'None'"
                }
              }
            }
          }
        }
      ]
    },
    "drillFilterOtherVisuals": true
  }
}
```



# Version 2

This is a Power BI visual definition file for a **table visual**. Here's what the main sections mean:

**Basic Properties:**

- `visualType: "tableEx"` - Extended table visual
- `position` - Location and size on the report canvas (x, y coordinates, width, height)

**Query Section:**

- `projections` - Defines the 10 columns displayed: Quality Index, Apple1-7, Percentage (sum), and Date Update (all from `prod_data` table)
- `sortDefinition` - Table is sorted by Quality Index in ascending order

**Formatting (objects):**

- `columnWidth` - Column width settings for each field
- `columnHeaders` - Auto-sizes column widths
- `columnFormatting` - Custom styling enabled for Quality Index values

**Conditional Formatting:**
The `values` section contains conditional background color rules for the Apple1 column:

- **"Passed"** → Green (#2DD74B)
- **"Not Passed"** → Orange (#eb895f)
- **"N/A"** → Gray (#cccccc)
- **Empty string** → Light gray (#e6e6e6)

This creates a color-coded table where quality status is visually indicated through cell background colors, making it easy to spot passed/failed items at a glance.

```json
{
  "$schema": "https://developer.microsoft.com/json-schemas/fabric/item/report/definition/visualContainer/2.5.0/schema.json",
  "name": "ed733890a646ec881fb2",
  "position": {
    "x": 111.24744376278119,
    "y": 123.02658486707567,
    "z": 1000,
    "height": 348.13905930470349,
    "width": 999.918200408998,
    "tabOrder": 0
  },
  "visual": {
    "visualType": "tableEx",
    "query": {
      "queryState": {
        "Values": {
          "projections": [
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Quality Index"
                }
              },
              "queryRef": "prod_data.Quality Index",
              "nativeQueryRef": "Quality Index"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple7"
                }
              },
              "queryRef": "prod_data.Apple7",
              "nativeQueryRef": "Apple7"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple4"
                }
              },
              "queryRef": "prod_data.Apple4",
              "nativeQueryRef": "Apple4"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple1"
                }
              },
              "queryRef": "prod_data.Apple 1",
              "nativeQueryRef": "Apple1"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple2"
                }
              },
              "queryRef": "prod_data.Apple2",
              "nativeQueryRef": "Apple2"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple3"
                }
              },
              "queryRef": "prod_data.Apple3",
              "nativeQueryRef": "Apple3"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple6"
                }
              },
              "queryRef": "prod_data.Apple6",
              "nativeQueryRef": "Apple6"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Apple5"
                }
              },
              "queryRef": "prod_data.Apple5",
              "nativeQueryRef": "Apple5"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Percentage"
                }
              },
              "queryRef": "Sum(prod_data.Percentage)",
              "nativeQueryRef": "Percentage"
            },
            {
              "field": {
                "Column": {
                  "Expression": {
                    "SourceRef": {
                      "Entity": "prod_data"
                    }
                  },
                  "Property": "Date Update"
                }
              },
              "queryRef": "prod_data.Date Update",
              "nativeQueryRef": "Date Update"
            }
          ],
          "showAll": true
        }
      },
      "sortDefinition": {
        "sort": [
          {
            "field": {
              "Column": {
                "Expression": {
                  "SourceRef": {
                    "Entity": "prod_data"
                  }
                },
                "Property": "Quality Index"
              }
            },
            "direction": "Ascending"
          }
        ]
      }
    },
    "objects": {
      "columnWidth": [
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple7"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple6"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Quality Index"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple 1"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple2"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple3"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple4"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Apple5"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "Sum(prod_data.Percentage)"
          }
        },
        {
          "properties": {},
          "selector": {
            "metadata": "prod_data.Date Update"
          }
        }
      ],
      "columnFormatting": [
        {
          "properties": {
            "styleHeader": {
              "expr": {
                "Literal": {
                  "Value": "false"
                }
              }
            },
            "styleTotal": {
              "expr": {
                "Literal": {
                  "Value": "false"
                }
              }
            },
            "styleValues": {
              "expr": {
                "Literal": {
                  "Value": "true"
                }
              }
            }
          },
          "selector": {
            "metadata": "prod_data.Quality Index"
          }
        }
      ],
      "columnHeaders": [
        {
          "properties": {
            "autoSizeColumnWidth": {
              "expr": {
                "Literal": {
                  "Value": "true"
                }
              }
            }
          }
        }
      ],
      "values": [
        {
          "properties": {}
        },
        {
          "properties": {
            "backColor": {
              "solid": {
                "color": {
                  "expr": {
                    "Conditional": {
                      "Cases": [
                        {
                          "Condition": {
                            "Comparison": {
                              "ComparisonKind": 0,
                              "Left": {
                                "Aggregation": {
                                  "Expression": {
                                    "Column": {
                                      "Expression": {
                                        "SourceRef": {
                                          "Entity": "prod_data"
                                        }
                                      },
                                      "Property": "Apple1"
                                    }
                                  },
                                  "Function": 3
                                }
                              },
                              "Right": {
                                "Literal": {
                                  "Value": "'Passed'"
                                }
                              }
                            },
                            "Annotations": {
                              "PowerBI.SQExprEvaluationKind": 1,
                              "PowerBI.SQExprTextOperatorOption": 2
                            }
                          },
                          "Value": {
                            "Literal": {
                              "Value": "'#2DD74B'"
                            }
                          }
                        },
                        {
                          "Condition": {
                            "Comparison": {
                              "ComparisonKind": 0,
                              "Left": {
                                "Aggregation": {
                                  "Expression": {
                                    "Column": {
                                      "Expression": {
                                        "SourceRef": {
                                          "Entity": "prod_data"
                                        }
                                      },
                                      "Property": "Apple1"
                                    }
                                  },
                                  "Function": 3
                                }
                              },
                              "Right": {
                                "Literal": {
                                  "Value": "'Not Passed'"
                                }
                              }
                            },
                            "Annotations": {
                              "PowerBI.SQExprEvaluationKind": 1,
                              "PowerBI.SQExprTextOperatorOption": 2
                            }
                          },
                          "Value": {
                            "Literal": {
                              "Value": "'#eb895f'"
                            }
                          }
                        },
                        {
                          "Condition": {
                            "Comparison": {
                              "ComparisonKind": 0,
                              "Left": {
                                "Aggregation": {
                                  "Expression": {
                                    "Column": {
                                      "Expression": {
                                        "SourceRef": {
                                          "Entity": "prod_data"
                                        }
                                      },
                                      "Property": "Apple1"
                                    }
                                  },
                                  "Function": 3
                                }
                              },
                              "Right": {
                                "Literal": {
                                  "Value": "'N/A'"
                                }
                              }
                            },
                            "Annotations": {
                              "PowerBI.SQExprEvaluationKind": 1,
                              "PowerBI.SQExprTextOperatorOption": 2
                            }
                          },
                          "Value": {
                            "Literal": {
                              "Value": "'#cccccc'"
                            }
                          }
                        },
                        {
                          "Condition": {
                            "Comparison": {
                              "ComparisonKind": 0,
                              "Left": {
                                "Aggregation": {
                                  "Expression": {
                                    "Column": {
                                      "Expression": {
                                        "SourceRef": {
                                          "Entity": "prod_data"
                                        }
                                      },
                                      "Property": "Apple1"
                                    }
                                  },
                                  "Function": 3
                                }
                              },
                              "Right": {
                                "Literal": {
                                  "Value": "''"
                                }
                              }
                            },
                            "Annotations": {
                              "PowerBI.SQExprEvaluationKind": 1,
                              "PowerBI.SQExprTextOperatorOption": 11
                            }
                          },
                          "Value": {
                            "Literal": {
                              "Value": "'#e6e6e6'"
                            }
                          }
                        }
                      ]
                    }
                  }
                }
              }
            }
          },
          "selector": {
            "data": [
              {
                "dataViewWildcard": {
                  "matchingOption": 1
                }
              }
            ],
            "metadata": "prod_data.Apple 1"
          }
        }
      ]
    },
    "visualContainerObjects": {
      "stylePreset": [
        {
          "properties": {
            "name": {
              "expr": {
                "Literal": {
                  "Value": "'None'"
                }
              }
            }
          }
        }
      ]
    },
    "drillFilterOtherVisuals": true
  }
}
```



## in which part of the code were added the sorting of Apple1-7 columns by Count value (from Quality Index Column)

However, this sorts the table ROWS by Quality Index, not the columns themselves.

The column order (Quality Index, Apple7, Apple4, Apple1, Apple2, Apple3, Apple6, Apple5) is determined by the sequence in the projections array (lines 15-169). The Apple columns appear in a specific order there, but there's no "sort by count" logic for column ordering in this definition—columns are simply displayed in the order they're listed in the projections.

If you want to sort columns by a specific logic, that would need to be done by reordering the items in the projections array or using a different approach in the data model.

```json
"sortDefinition": {
  "sort": [
    {
      "field": {
        "Column": {
          "Expression": {
            "SourceRef": {
              "Entity": "prod_data"
            }
          },
          "Property": "Quality Index"
        }
      },
      "direction": "Ascending"
    }
  ]
}
```

