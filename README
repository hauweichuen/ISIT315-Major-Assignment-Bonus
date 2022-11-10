# ISIT315 Major Assignment (Additional Task)

Created by Wei Chuen Hau (Student Number: 7756793).

## Run Fuseki Server

---

Execute `fuseki-server --file=ValuesMapOntology.owl /ValuesMapOntology.owl` in root directory.

## SPARQL Endpoint

---

The SPARQL Endpoint will be located at `http://localhost:3030/ValuesMapOntology.owl/sparql`. Use any SPARQL client to query the endpoint or use the web interface stated below.

## Access SPARQL Endpoint through Web Interface

---

1\. Go to `http://localhost:3030/` after running the Fuseki Server.  
2\. Click on `query` for the row with the name `/ValuesMapOntology.owl`.  
3\. Type and click on `Run query` (Play button at the top right corner of editor) to exexute the query.

## Example SPARQL Queries

---

### 1. Find for all human values associated to the right to basic information about processing

```
PREFIX : <http://www.semanticweb.org/hauweichuen/ontologies/2022/9/valuesMapOntology#>
PREFIX gdpr: <http://www.semanticweb.org/hauweichuen/ontologies/2022/9/GDPROntology#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX gdprtext: <https://w3id.org/GDPRtEXT#>

SELECT DISTINCT ?humanValue WHERE {
  ?humanValue rdfs:subClassOf ?valueProperty .
  {
    {
      ?valueProperty owl:onProperty :hasImplicitLinkToPrinciple;
                     owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasImplicitLinkToPrinciple;
                     owl:someValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasExplicitLinkToPrinciple;
                     owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasExplicitLinkToPrinciple;
                     owl:someValuesFrom ?principle .
    }
  }
  {
    gdprtext:RightToBasicInformationAboutProcessing rdfs:subClassOf ?rightsProperty .
    {
      ?rightsProperty owl:onProperty gdpr:rightsDirectlyLinkedToPrinciple;
                    owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDirectlyLinkedToPrinciple;
                    owl:someValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDerivedLinkedToPrinciple;
                    owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDerivedLinkedToPrinciple;
                    owl:someValuesFrom ?principle .
    }
  }
}
```

### 2. Find for all rights associated to the conformity-rules human value

```
PREFIX : <http://www.semanticweb.org/hauweichuen/ontologies/2022/9/valuesMapOntology#>
PREFIX humanValues: <http://www.semanticweb.org/hauweichuen/ontologies/2022/9/humanValues#>
PREFIX gdpr: <http://www.semanticweb.org/hauweichuen/ontologies/2022/9/GDPROntology#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX gdprtext: <https://w3id.org/GDPRtEXT#>

SELECT DISTINCT ?rights WHERE {
  ?rights rdfs:subClassOf ?rightsProperty .
  {
    {
      ?rightsProperty owl:onProperty gdpr:rightsDirectlyLinkedToPrinciple;
                    owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDirectlyLinkedToPrinciple;
                    owl:someValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDerivedLinkedToPrinciple;
                    owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDerivedLinkedToPrinciple;
                    owl:someValuesFrom ?principle .
    }
  }
  {
    humanValues:Rules rdfs:subClassOf ?valueProperty .
    {
      ?valueProperty owl:onProperty :hasImplicitLinkToPrinciple;
                     owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasImplicitLinkToPrinciple;
                     owl:someValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasExplicitLinkToPrinciple;
                     owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasExplicitLinkToPrinciple;
                     owl:someValuesFrom ?principle .
    }
  }
}
```

### 3. Find for all human values associated to the right to basic information about processing, including those associated through rights sub provisions

```
PREFIX : <http://www.semanticweb.org/hauweichuen/ontologies/2022/9/valuesMapOntology#>
PREFIX gdpr: <http://www.semanticweb.org/hauweichuen/ontologies/2022/9/GDPROntology#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX gdprtext: <https://w3id.org/GDPRtEXT#>
SELECT DISTINCT ?humanValue WHERE {
  ?humanValue rdfs:subClassOf ?valueProperty .
  {
    {
      ?valueProperty owl:onProperty :hasImplicitLinkToPrinciple;
                     owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasImplicitLinkToPrinciple;
                     owl:someValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasExplicitLinkToPrinciple;
                     owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasExplicitLinkToPrinciple;
                     owl:someValuesFrom ?principle .
    }
  }
  gdprtext:RightToBasicInformationAboutProcessing rdfs:subClassOf ?rightsProperty .
  {
    {
      ?rightsProperty owl:onProperty gdpr:rightsDirectlyLinkedToPrinciple;
                      owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDirectlyLinkedToPrinciple;
                      owl:someValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDerivedLinkedToPrinciple;
                      owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDerivedLinkedToPrinciple;
                      owl:someValuesFrom ?principle .
    }
  }
  UNION {
    OPTIONAL {
      {
        ?rightsProperty owl:onProperty gdpr:hasSubProvision;
                        owl:someValuesFrom ?subRights .
      }
      UNION
      {
        ?rightsProperty owl:onProperty gdpr:hasSubProvision;
                        owl:allValuesFrom ?subRights .
      }
      ?subRights rdfs:subClassOf ?subRightsProperty .
      {
        ?subRightsProperty owl:onProperty gdpr:subRightsDirectlyLinkedToPrinciple;
                           owl:allValuesFrom ?principle .
      }
      UNION
      {
        ?subRightsProperty owl:onProperty gdpr:subRightsDirectlyLinkedToPrinciple;
                           owl:someValuesFrom ?principle .
      }
      UNION
      {
        ?subRightsProperty owl:onProperty gdpr:subRightsDerivedLinkedToPrinciple;
                           owl:allValuesFrom ?principle .
      }
      UNION
      {
        ?subRightsProperty owl:onProperty gdpr:subRightsDerivedLinkedToPrinciple;
                           owl:someValuesFrom ?principle .
      }
    }
  }
}
```

### 4. Find for all rights associated to the power-resources human value, including those associated through rights sub provisions

```
PREFIX : <http://www.semanticweb.org/hauweichuen/ontologies/2022/9/valuesMapOntology#>
PREFIX humanValues: <http://www.semanticweb.org/hauweichuen/ontologies/2022/9/humanValues#>
PREFIX gdpr: <http://www.semanticweb.org/hauweichuen/ontologies/2022/9/GDPROntology#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX gdprtext: <https://w3id.org/GDPRtEXT#>
SELECT DISTINCT ?rights WHERE {
  ?rights rdfs:subClassOf ?rightsProperty .
  {
    {
      ?rightsProperty owl:onProperty gdpr:rightsDirectlyLinkedToPrinciple;
                      owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDirectlyLinkedToPrinciple;
                      owl:someValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDerivedLinkedToPrinciple;
                      owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?rightsProperty owl:onProperty gdpr:rightsDerivedLinkedToPrinciple;
                      owl:someValuesFrom ?principle .
    }
  }
  UNION {
    OPTIONAL {
      {
        ?rightsProperty owl:onProperty gdpr:hasSubProvision;
                        owl:someValuesFrom ?subRights .
      }
      UNION
      {
        ?rightsProperty owl:onProperty gdpr:hasSubProvision;
                        owl:allValuesFrom ?subRights .
      }
      ?subRights rdfs:subClassOf ?subRightsProperty .
      {
        ?subRightsProperty owl:onProperty gdpr:subRightsDirectlyLinkedToPrinciple;
                           owl:allValuesFrom ?principle .
      }
      UNION
      {
        ?subRightsProperty owl:onProperty gdpr:subRightsDirectlyLinkedToPrinciple;
                           owl:someValuesFrom ?principle .
      }
      UNION
      {
        ?subRightsProperty owl:onProperty gdpr:subRightsDerivedLinkedToPrinciple;
                           owl:allValuesFrom ?principle .
      }
      UNION
      {
        ?subRightsProperty owl:onProperty gdpr:subRightsDerivedLinkedToPrinciple;
                           owl:someValuesFrom ?principle .
      }
    }
  }
  {
    humanValues:Resources rdfs:subClassOf ?valueProperty .
    {
      ?valueProperty owl:onProperty :hasImplicitLinkToPrinciple;
                     owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasImplicitLinkToPrinciple;
                     owl:someValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasExplicitLinkToPrinciple;
                     owl:allValuesFrom ?principle .
    }
    UNION
    {
      ?valueProperty owl:onProperty :hasExplicitLinkToPrinciple;
                     owl:someValuesFrom ?principle .
    }
  }
}
```
