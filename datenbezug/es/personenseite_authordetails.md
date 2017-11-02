

**Personenseite (authordetails)**

http://locallinked.swissbib.ch/Exploration/AuthorDetails?lookfor=http://data.swissbib.ch/person/2b8fcc4a-c43a-3e12-8cb9-afc1c21aa6aa&type=AuthorForId
erste abgesetzte Query

damit wird das template elasticsearch/authordetails gefüllt da zwei Typen von Elasticsearch abgefragt werden (bibliographicResource / person) enthält die collection (wenn Datem gefunden werden) aus beiden Queries Entities. Im konkreten Fall bei mir im Test; 20 bibliographicResource und 1 person

das führt dazu, dass im Template nach diesen unterschiedlichen Typen differenziert wird (alle Personentypen und "der Rest", für den man deann nicht mehr differenziert)


{"index":"lsb","type":"person"}
{"query":{"multi_match":{"fields":["@id"],"type":"cross_fields","operator":"and","query":"http:\/\/data.swissbib.ch\/person\/2b8fcc4a-c43a-3e12-8cb9-afc1c21aa6aa"}}}
{"index":"lsb","type":"bibliographicResource"}
{"query":{"multi_match":{"fields":["dct:contributor"],"type":"cross_fields","operator":"and","query":"http:\/\/data.swissbib.ch\/person\/2b8fcc4a-c43a-3e12-8cb9-afc1c21aa6aa"}},"size": 20,"from": 0}

    $instances = array();
    $basePath = $this->basePath();

    $results = $this->results->getResults();
    foreach ($results as $singleResult):
        if ($singleResult->isPerson()) {
            $person_uniqueId = $singleResult->getUniqueID();
            $person_alternativeNames = $singleResult->getAlternativeNames();
            $person_biography = $singleResult->getBiography();
            $person_birthDate = $singleResult->getBirthDate();
            $person_birthPlace = $singleResult->getBirthPlace();
            $person_deathDate = $singleResult->getDeathDate();
            $person_deathPlace = $singleResult->getDeathPlace();
            $person_externalLinks = $singleResult->getPersonExternalLinks();
            $person_genreAsLiteral = $singleResult->getGenreAsLiteral();
            $person_genreAsUri = $singleResult->getGenreAsUri();
            $person_influenced = $singleResult->getInfluenced();
            $person_influencedBy = $singleResult->getInfluencedBy();
            $person_movementAsLiteral = $singleResult->getMovementAsLiteral();
            $person_movementAsUri = $singleResult->getMovementAsUri();
            $person_nameAsString = $singleResult->getNameAsString();
            $person_nationality = $singleResult->getNationality();
            $person_notableWork = $singleResult->getNotableWork();
            $person_occupation = $singleResult->getOccupation();
            $person_partner = $singleResult->getPartner();
            $person_pseudonym = $singleResult->getPseudonym();
            $person_spouse = $singleResult->getSpouse();
            $person_thumbnail = $singleResult->getThumbnail();
        } else
            $instances[] = $singleResult;
    endforeach;