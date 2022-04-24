```{mermaid}

    flowchart TD
        
        covid_victims([Covid Victims]) --- covid_victims_covid_victim[Covid Victim]
        click covid_victims_covid_victim href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/covid_victims/covid_victim-profile.html" "Profile"
        
        scimago_journals([Scimago Journals]) --- scimago_journals_journal[Journal]
        click scimago_journals_journal href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/scimago_journals/journal-profile.html" "Profile"
        
        pypi_downloads([Pypi Downloads]) --- pypi_downloads_download[Download]
        click pypi_downloads_download href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/pypi_downloads/download-profile.html" "Profile"
        
        repec_via_nep([RePEc via NEP]) --- repec_via_nep_paper[Paper]
        click repec_via_nep_paper href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/paper-profile.html" "Profile"
        
        repec_via_nep([RePEc via NEP]) --- repec_via_nep_nep[Nep]
        click repec_via_nep_nep href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep-profile.html" "Profile"
        
        repec_via_nep([RePEc via NEP]) --- repec_via_nep_nep_inclusion[Nep Inclusion]
        click repec_via_nep_nep_inclusion href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep_inclusion-profile.html" "Profile"
        
        repec_via_nep([RePEc via NEP]) --- repec_via_nep_nep_issue[Nep Issue]
        click repec_via_nep_nep_issue href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/nep_issue-profile.html" "Profile"
        
        repec_via_nep([RePEc via NEP]) --- repec_via_nep_authorship[Authorship]
        click repec_via_nep_authorship href "https://s3.eu-de.cloud-object-storage.appdomain.cloud/sscub-public-explorer/repec_via_nep/authorship-profile.html" "Profile"
        
```