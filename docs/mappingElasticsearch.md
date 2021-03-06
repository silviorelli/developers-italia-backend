## Mappings Elasticsearch

**Data mapping (ES):**

1.  <mapping-software>
2.  <mapping-amministrazioni>
3.  <alias>

**software**

```{
"mappings": {
  "software": {
    "dynamic_templates": [
      {
        "description": {
          "path_match": "description.*",
          "mapping": {
            "type": "object",
            "properties": {
              "localisedName": {
                "type": "text"
              },
              "genericName": {
                "type": "text",
                "fields": {
                  "keyword": { "type": "keyword", "ignore_above": 256 }
                }
              },
              "shortDescription": {
                "type": "text"
              },
              "longDescription": {
                "type": "text"
              },
              "documentation": {
                "type": "text",
                "index": false
              },
              "apiDocumentation": {
                "type": "text",
                "index": false
              },
              "featureList": {
                "type": "keyword"
              },
              "freeTags": {
                "type": "keyword"
              },
              "screenshots": {
                "type": "keyword",
                "index": false
              },
              "videos": {
                "type": "keyword",
                "index": false
              },
              "awards": {
                "type": "keyword"
              }
            }
          }
        }
      }
    ],
    "properties": {
      "fileRawURL": {
        "type": "text",
        "index": false
      },
      "it-riuso-codiceIPA-label": {
        "type": "text"
      },
      "publiccode-yaml-version": {
        "type": "text",
        "index": false
      },
      "name": {
        "type": "text"
      },
      "applicationSuite": {
        "type": "text",
        "fields": { "keyword": { "type": "keyword", "ignore_above": 256 } }
      },
      "url": {
        "type": "text",
        "index": false,
        "fields": { "keyword": { "type": "keyword", "ignore_above": 256 } }
      },
      "landingURL": {
        "type": "text",
        "index": false
      },
      "isBasedOn": {
        "type": "text",
        "index": false
      },
      "softwareVersion": {
        "type": "keyword"
      },
      "releaseDate": {
        "type": "date",
        "format": "strict_date"
      },
      "logo": {
        "type": "text",
        "index": false
      },
      "monochromeLogo": {
        "type": "text",
        "index": false
      },
      "inputTypes": {
        "type": "keyword"
      },
      "outputTypes": {
        "type": "keyword"
      },
      "platforms": {
        "type": "keyword"
      },
      "tags": {
        "type": "keyword"
      },
      "usedBy": {
        "type": "text",
        "fields": { "keyword": { "type": "keyword", "ignore_above": 256 } }
      },
      "roadmap": {
        "type": "text",
        "index": false
      },
      "developmentStatus": {
        "type": "keyword"
      },
      "softwareType": {
        "type": "keyword"
      },
      "intendedAudience-onlyFor": {
        "type": "keyword"
      },
      "intendedAudience-countries": {
        "type": "keyword"
      },
      "intendedAudience-unsupportedCountries": {
        "type": "keyword"
      },
      "legal-license": {
        "type": "text",
        "fields": { "keyword": { "type": "keyword", "ignore_above": 256 } }
      },
      "legal-mainCopyrightOwner": {
        "type": "text"
      },
      "legal-repoOwner": {
        "type": "text"
      },
      "legal-authorsFile": {
        "type": "text",
        "index": false
      },
      "maintenance-type": {
        "type": "keyword"
      },
      "maintenance-contractors": {
        "type": "nested",
        "properties": {
          "name": {
            "type": "text"
          },
          "until": {
            "type": "date",
            "format": "strict_date"
          },
          "website": {
            "type": "text",
            "index": false
          }
        }
      },
      "maintenance-contacts": {
        "type": "nested",
        "properties": {
          "name": {
            "type": "text"
          },
          "email": {
            "type": "text"
          },
          "phone": {
            "type": "text",
            "index": false
          },
          "affiliation": {
            "type": "text"
          }
        }
      },
      "localisation-localisationReady": {
        "type": "boolean"
      },
      "localisation-availableLanguages": {
        "type": "keyword"
      },
      "dependsOn-open": {
        "type": "nested",
        "properties": {
          "name": {
            "type": "text"
          },
          "version-min": {
            "type": "text",
            "index": false
          },
          "version-max": {
            "type": "text",
            "index": false
          },
          "version": {
            "type": "text",
            "index": false
          },
          "optional": {
            "type": "boolean"
          }
        }
      },
      "dependsOn-proprietary": {
        "type": "nested",
        "properties": {
          "name": {
            "type": "text"
          },
          "version-min": {
            "type": "text",
            "index": false
          },
          "version-max": {
            "type": "text",
            "index": false
          },
          "version": {
            "type": "text",
            "index": false
          },
          "optional": {
            "type": "boolean"
          }
        }
      },
      "dependsOn-hardware": {
        "type": "nested",
        "properties": {
          "name": {
            "type": "text"
          },
          "version-min": {
            "type": "text",
            "index": false
          },
          "version-max": {
            "type": "text",
            "index": false
          },
          "version": {
            "type": "text",
            "index": false
          },
          "optional": {
            "type": "boolean"
          }
        }
      },
      "it-conforme-accessibile": {
        "type": "boolean"
      },
      "it-conforme-interoperabile": {
        "type": "boolean"
      },
      "it-conforme-sicuro": {
        "type": "boolean"
      },
      "it-conforme-privacy": {
        "type": "boolean"
      },
      "it-spid": {
        "type": "boolean"
      },
      "it-cie": {
        "type": "boolean"
      },
      "it-anpr": {
        "type": "boolean"
      },
      "it-pagopa": {
        "type": "boolean"
      },
      "it-riuso-codiceIPA": {
        "type": "keyword"
      },
      "it-ecosistemi": {
        "type": "keyword"
      },
      "it-designKit-seo": {
        "type": "boolean"
      },
      "it-designKit-ui": {
        "type": "boolean"
      },
      "it-designKit-web": {
        "type": "boolean"
      },
      "it-designKit-content": {
        "type": "boolean"
      },
      "suggest-name": {
        "type": "completion"
      },
      "vitality-score": {
        "type": "text",
        "index": false
      },
      "vitality-dataChart": {
        "type": "integer"
      },
      "related-software": {
        "properties": {
          "name": {
            "type": "text",
            "index": false
          },
          "image": {
            "type": "text",
            "index": false
          },
          "eng": {
            "properties": {
              "localised-name": {
                "type": "text",
                "index": false
              },
              "url": {
                "type": "text",
                "index": false
              }
            }
          },
          "ita": {
            "properties": {
              "localised-name": {
                "type": "text",
                "index": false
              },
              "url": {
                "type": "text",
                "index": false
              }
            }
          }
        }
      },
      "tags-related": {
        "type": "keyword"
      },
      "popular-tags": {
        "type": "keyword"
      },
      "share-tags": {
        "type": "keyword"
      },
      "old-variant": {
        "properties": {
          "name": {
            "type": "text",
            "index": false
          },
          "eng": {
            "properties": {
              "localised-name": {
                "type": "text",
                "index": false
              },
              "url": {
                "type": "text",
                "index": false
              },
              "feature-list": {
                "type": "keyword",
                "index": false
              },
              "vitality-score": {
                "type": "integer",
                "index": false
              },
              "legal-repo-owner": {
                "type": "text",
                "index": false
              }
            }
          },
          "ita": {
            "properties": {
              "localised-name": {
                "type": "text",
                "index": false
              },
              "url": {
                "type": "text",
                "index": false
              },
              "feature-list": {
                "type": "keyword",
                "index": false
              },
              "vitality-score": {
                "type": "integer",
                "index": false
              },
              "legal-repo-owner": {
                "type": "text",
                "index": false
              }
            }
          }
        }
      },
      "old-feature-list": {
        "properties": {
          "ita": {
            "type": "keyword",
            "index": false
          },
          "eng": {
            "type": "keyword",
            "index": false
          }
        }
      }
    }
  }
}
}
```

**amministrazioni**

```{
"settings": {
"analysis": {
  "analyzer": {
    "suggest_analyzer": {
      "tokenizer": "suggest_tokenizer",
      "filter": ["lowercase"]
    }
  },
  "tokenizer": {
    "suggest_tokenizer": {
      "type": "ngram",
      "min_gram": 2,
      "max_gram": 10,
      "token_chars": ["letter", "digit"]
    }
  }
}
},
"mappings": {
"administration": {
  "properties": {
    "it-riuso-codiceIPA": {
      "type": "keyword"
    },
    "it-riuso-codiceIPA-label": {
      "type": "text",
      "fields": {
        "ngram": {
          "type": "text",
          "analyzer": "suggest_analyzer"
        }
      }
    }
  }
}
}
}
```

**alias**

The main alias is `publiccode`. It alias software and amministrazioni.
