```mermaid
graph TB "CPAN Ecosystem"
  subgraph "Author"
    %%git_push["git push"]
    %%pause_upload["pause upload"]
    subgraph "SBOM::Author"
      field1
      field2
    end
  end
  subgraph "Central git repository"
    %%git_push --> git_repo["git@github.com/author/foo-bar.git"]
    subgraph "SBOM::Repository"
      field3
      field4
    end
  end
  subgraph "The CPAN Ecosystem"
    subgraph "Patcher (CPAN)"
      %%MyApp["My::App"] --> FooBar_patch["Foo::Bar-1.0-security.patch"]
      subgraph "SBOM::Patcher"
        field7
        field8
      end
    end
    subgraph "Curator (CPAN)"
      %%pkg_cpan --> pkg_cpan_mycorp["pkg:cpan/AUTHOR/Foo-Bar?repository_url=cpan.mycorp.example"]
      subgraph "SBOM::Curator"
        field15
        field16
      end
    end
    subgraph "Distributor (CPAN)"
      %%pause_upload --> AUTHOR_FooBar["AUTHOR/Foo-Bar-1.0.tar.gz"]
      %%pause_upload --> pkg_cpan_mycorp
      %%FooBar_patch --> AUTHOR_FooBar_patch["AUTHOR/Foo-Bar-1.0-patch.tar.gz"]
      %%FooBar_patch --> pkg_cpan_patch["pkg:cpan/AUTHOR/Foo-Bar@1.0-patch?repository_url=cpan.mycorp.example"]
      subgraph "SBOM::Distributor"
        field11
        field12
      end
    end
  end
  subgraph "Developer"
    %% pkg_apt_mycorp["pkg:apt/ubuntu/libfoobar-perl?repository_url=apt.mycorp.example"] --> MyApp
    %% pkg_cpan_mycorp --> MyApp
    subgraph "SBOM::Developer"
      field19
      field20
    end
  end
  subgraph "Security Reviewer"
    %% pentest_approve["pentest approve my-app"]
    subgraph "SBOM::Reviewer"
      field21
      field22
    end
  end
  subgraph "Quality Assurance / Tester"
    %% prove_myapp["prove ./my-app"]
    subgraph "SBOM::Tester"
      field23
      field24
    end
  end
  subgraph "SecOps"
    %% cpan_audit["cpan-audit ./my-app"]
    subgraph "SBOM::SecOps"
      field25
      field26
    end
  end
  subgraph "Deployer"
    %% carton_install["carton install --deployment ./my-app"]
    subgraph "SBOM::Deployer"
      field27
      field28
    end
  end
  subgraph "Consumer"
    subgraph "SBOM::Consumer"
      field29
      field30
    end
  end
  subgraph "Auditor"
    subgraph "SBOM::Auditor"
      field31
      field32
    end
  end
  ```