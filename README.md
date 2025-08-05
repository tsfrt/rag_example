# fedramp_mod_rag

This is an example RAG Architecture that creates the infrastructure to support RAG/Agent solutions on Databricks using the subset of capabilities available with the FedRamp Mod Enhanced Security and Compliance add-on.

The solution includes the following
* A PDF parsing/chunking solution that handles complex PDFs with images and diagrams
* Calculating embeddings and loading an external vector store
* Creating a proxy model endpoint that handles preparing (embeddings) and querying an external vector store
* Exposing a UC Function for each vector endpoint that can be used with Databricks Playground to rapidly prototype RAG/Agent workflows
* Databricks Asset Bundle and Gihub Actions integrations

This functionality will be unecessary as `ai_parse_document` and integrated `vector index` funcationality become available with the FedRamp Mod ESC.

## Getting started

1. Install the Databricks CLI from https://docs.databricks.com/dev-tools/cli/databricks-cli.html

2. Authenticate to your Databricks workspace, if you have not done so already:
    ```
    $ databricks configure
    ```

3. To deploy a development copy of this project, type:
    ```
    $ databricks bundle deploy --target dev
    ```
    (Note that "dev" is the default target, so the `--target` parameter
    is optional here.)

    This deploys everything that's defined for this project.
    For example, the default template would deploy a job called
    `[dev yourname] fedramp_mod_rag_job` to your workspace.
    You can find that job by opening your workpace and clicking on **Workflows**.

4. Similarly, to deploy a production copy, type:
   ```
   $ databricks bundle deploy --target prod
   ```

   Note that the default job from the template has a schedule that runs every day
   (defined in resources/fedramp_mod_rag.job.yml). The schedule
   is paused when deploying in development mode (see
   https://docs.databricks.com/dev-tools/bundles/deployment-modes.html).

5. To run a job or pipeline, use the "run" command:
   ```
   $ databricks bundle run
   ```

6. Optionally, install developer tools such as the Databricks extension for Visual Studio Code from
   https://docs.databricks.com/dev-tools/vscode-ext.html. Or read the "getting started" documentation for
   **Databricks Connect** for instructions on running the included Python code from a different IDE.

7. For documentation on the Databricks asset bundles format used
   for this project, and for CI/CD configuration, see
   https://docs.databricks.com/dev-tools/bundles/index.html.
