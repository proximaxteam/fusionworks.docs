# Knowledge Base and Document Maintenance

### 1. Viewing Text Segments

Each document uploaded to the knowledge base is stored in the form of text segments (Chunks). You can view the specific text content of each segment in the segment list.

<figure><img src="../../.gitbook/assets/upload_segment.png" alt=""><figcaption><p>Viewing uploaded document segments</p></figcaption></figure>

***

### 2. Checking Segment Quality

The quality of document segmentation significantly affects the Q\&A performance of the knowledge base application. It is recommended to manually check the segment quality before associating the knowledge base with the application.

Although automated segmentation methods based on character length, identifiers, or NLP semantic segmentation can significantly reduce the workload of large-scale text segmentation, the quality of segmentation is related to the text structure of different document formats and the semantic context. Manual checking and correction can effectively compensate for the shortcomings of machine segmentation in semantic recognition.

When checking segment quality, pay attention to the following situations:

* **Overly short text segments**, leading to semantic loss;

<figure><img src="../../.gitbook/assets/guides/knowledge-base/image (183).png" alt="" width="373"><figcaption><p>Overly short text segments</p></figcaption></figure>

* **Overly long text segments**, leading to semantic noise affecting matching accuracy;

<figure><img src="../../.gitbook/assets/over_long.png" alt="" width="327"><figcaption><p>Overly long text segments</p></figcaption></figure>

* **Obvious semantic truncation**, which occurs when using maximum segment length limits, leading to forced semantic truncation and missing content during recall;

<figure><img src="../../.gitbook/assets/guides/knowledge-base/image (185).png" alt="" width="357"><figcaption><p>Obvious semantic truncation</p></figcaption></figure>

***

### 3. Adding Text Segments

In the segment list, click "Add Segment" to add one or multiple custom segments to the document.

<figure><img src="../../.gitbook/assets/addd_new.png" alt=""><figcaption></figcaption></figure>

When adding segments in bulk, you need to first download the CSV format segment upload template, edit all the segment content in Excel according to the template format, save the CSV file, and then upload it.

<figure><img src="../../.gitbook/assets/batch.png" alt=""><figcaption><p>Bulk adding custom segments</p></figcaption></figure>

***

### 4. Editing Text Segments

In the segment list, you can directly edit the content of the added segments, including the text content and keywords of the segments.

<figure><img src="../../.gitbook/assets/edit.png" alt=""><figcaption><p>Editing document segments</p></figcaption></figure>

***

### 5. Metadata Management

In addition to marking metadata information from different source documents, such as the title, URL, keywords, and description of web data, metadata will be used in the segment recall process of the knowledge base as structured fields for recall filtering or displaying citation sources.

{% hint style="info" %}
The metadata filtering and citation source functions are not yet supported in the current version.
{% endhint %}

<figure><img src="../../.gitbook/assets/metadata.png" alt=""><figcaption><p>Metadata management</p></figcaption></figure>

***

### 6. Adding Documents

In "Knowledge Base > Documents," click "Add File" to upload new documents or Notion pages to the created knowledge base.

A knowledge base (Knowledge) is a collection of documents (Documents). Documents can be uploaded by developers or operators, or synchronized from other data sources (usually corresponding to a file unit in the data source).

<figure><img src="../../.gitbook/assets/add_file.png" alt=""><figcaption><p>Uploading new documents to the knowledge base</p></figcaption></figure>

***

### 7. Document Disable and Archive

**Disable**: The dataset supports disabling documents or segments that are temporarily not to be indexed. In the dataset document list, click the disable button to disable the document. You can also disable an entire document or a specific segment in the document details. Disabled documents will not be indexed. Click enable on the disabled documents to cancel the disable status.

**Archive**: Old document data that is no longer in use can be archived if you do not want to delete it. Archived data can only be viewed or deleted, not edited. In the dataset document list, click the archive button to archive the document. You can also archive documents in the document details. Archived documents will not be indexed. Archived documents can also be unarchived.

***

### 8. Knowledge Base Settings

Click **Settings** in the top navigation of the knowledge base to change the following settings:

<figure><img src="../../.gitbook/assets/setting.png" alt=""><figcaption><p>Knowledge base settings</p></figcaption></figure>

**Knowledge Base Name**: Define a name to identify a knowledge base.

**Knowledge Base Description**: Used to describe the information represented by the documents in the knowledge base.

{% hint style="info" %}
When the recall mode of the knowledge base is N-Choose-1, the knowledge base is provided as a tool for LLM reasoning calls. The reasoning is based on the description of the knowledge base. If the description is empty, FusionWorks's automatic indexing strategy will be used.
{% endhint %}

**Visibility Permissions**: You can choose "Only Me" or "All Team Members." People without permissions will not be able to view and edit the dataset.

**Index Mode**: [Reference Document](./)

**Embedding Model**: Modify the embedding model of the knowledge base. Changing the embedding model will re-embed all documents in the knowledge base, and the original embeddings will be deleted.

**Retrieval Settings**: [Reference Document](./)

***
