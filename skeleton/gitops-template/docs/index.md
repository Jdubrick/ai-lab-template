# AI Software Template Gitops

This repository contains the necessary content required for managing Gitops. It was created as part of an AI Software Template. The associated source component is available for reference through the **Overview** tab. You can find an example of this below.

![Overview Tab](./images/overview-dependency)

## Deployment

{%- if values.existingModelServer %}
During the template setup a custom model server was entered. Therefore no model service was deployed by this application.

{%- else %}
Based on the input from the AI Software Template, a deployment with the following characterisics was made:

**Model Service:** [${{ values.modelServerName }}]({%- if values.vllmSelected %} ${{ values.modelServiceSrcVLLM }} {%- else %} ${{ values.modelServiceSrcOther }} {%- endif %})

**Port:** ${{ values.modelServicePort }}

{%- endif %}

{%- if values.supportApp %}

An application built from ${{ values.templateSource }} will be stored in *${{ values.imageRegistry }}/${{ values.imageOrg }}/${{ values.imageName }}* and deployed via Gitops. This application is accessible on port **${{ values.appPort }}**

{%- endif %}