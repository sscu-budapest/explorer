```{mermaid}

    flowchart LR
        
        covid_victims([Covid Victims]) --- covid_victims_covid_victim[Covid Victim]
        click covid_victims_covid_victim href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/covid_victims/covid_victim-profile.html" "Profile"
        
        scimago_journals([Scimago Journals]) --- scimago_journals_journal[Journal]
        click scimago_journals_journal href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/scimago_journals/journal-profile.html" "Profile"
        
        pypi_downloads([Pypi Downloads]) --- pypi_downloads_package_download[Package Download]
        click pypi_downloads_package_download href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/pypi_downloads/package_download-profile.html" "Profile"
        
        repec_via_nep([RePEc via NEP]) --- repec_via_nep_authorship[Authorship]
        click repec_via_nep_authorship href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/authorship-profile.html" "Profile"
        
        repec_via_nep([RePEc via NEP]) --- repec_via_nep_nep_inclusion[Nep Inclusion]
        click repec_via_nep_nep_inclusion href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep_inclusion-profile.html" "Profile"
        
        repec_via_nep([RePEc via NEP]) --- repec_via_nep_nep_issue[Nep Issue]
        click repec_via_nep_nep_issue href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep_issue-profile.html" "Profile"
        
        repec_via_nep([RePEc via NEP]) --- repec_via_nep_nep[Nep]
        click repec_via_nep_nep href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep-profile.html" "Profile"
        
        repec_via_nep([RePEc via NEP]) --- repec_via_nep_paper[Paper]
        click repec_via_nep_paper href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/paper-profile.html" "Profile"
        
        hungarian_elections([Hungarian Elections]) --- hungarian_elections_affiliation[Affiliation]
        click hungarian_elections_affiliation href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/affiliation-profile.html" "Profile"
        
        hungarian_elections([Hungarian Elections]) --- hungarian_elections_nominating_organization[Nominating Organization]
        click hungarian_elections_nominating_organization href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/nominating_organization-profile.html" "Profile"
        
        hungarian_elections([Hungarian Elections]) --- hungarian_elections_election[Election]
        click hungarian_elections_election href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/election-profile.html" "Profile"
        
        hungarian_elections([Hungarian Elections]) --- hungarian_elections_district_hierarchy[District Hierarchy]
        click hungarian_elections_district_hierarchy href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/district_hierarchy-profile.html" "Profile"
        
        hungarian_elections([Hungarian Elections]) --- hungarian_elections_geographical_unit[Geographical Unit]
        click hungarian_elections_geographical_unit href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/geographical_unit-profile.html" "Profile"
        
        hungarian_elections([Hungarian Elections]) --- hungarian_elections_election_precinct[Election Precinct]
        click hungarian_elections_election_precinct href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/election_precinct-profile.html" "Profile"
        
        hungarian_elections([Hungarian Elections]) --- hungarian_elections_vote_record[Vote Record]
        click hungarian_elections_vote_record href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/hungarian_elections/vote_record-profile.html" "Profile"
        
```