# TenderMe



## Synopsis
TenderMe is a software designed and developed to help people write their service descriptions. We do this by providing suggestions for the service description and a template for service description.



## Table of contents

> * [TenderMe](#title--repository-name)
>   * [Synopsis](#about--synopsis)
>   * [Table of contents](#table-of-contents)
>   * [Installation](#installation)
>   * [Usage](#usage)
>     * [Screenshots](#screenshots)
>     * [Features](#features)
>   * [Code](#code)
>     * [Content](#content)
>     * [Requirements](#requirements)
>     * [Limitations](#limitations)




---




## Installation

* ### Front-end
    Follow the instructions given below to install all the required packages on frontend side and launch the product on localhost:
    ```bash=
    cd TenderMe
    ng add .
    ng serve
    ```
    Now go to [http://localhost:4200/](http://localhost:4200/) on your browser to see the launched version of the product.
* ### Back-end
    The following commands can be used to install the Python packages for the backend side:
    ```bash=
    cd back-end
    pip install -r requirements.txt
    ```
    
    Next you will have to install ElasticSearch on your local machine by following the instructions on the ElasticSearch website [https://www.elastic.co/guide/en/elasticsearch/reference/current/install-elasticsearch.html](https://)
    
    After the installation, ElasticSearch should be now available on http://localhost:9200/. You can now start sending requests using python to build the index and fill it respectively with documents. Since our documents in this case are PDFs, we are using a pipeline that will facilitate converting PDFs into Base64 code to be able to store them in our index. You can install the plugin for the pipeline following the commands on this page: https://www.elastic.co/guide/en/elasticsearch/plugins/master/ingest-attachment.html

## Usage

### Features
* **Template** - A standard template for service description has been added with the button *'Vorlage'* on the navigation-bar of the homepage which can be used to access the template and download it. 
* **Search** - A search-bar has been added on the homepage which can be used as a search-engine for hundreds of service descriptions. You can search the required service description for reference by typing the relevant name on the search-bar and it will give you results based on your search.
* **Search-results** - The search-results can be accessed as well as downloaded as per user's needs.
* **Responsive web-pages** - All of the web-pages are responsive and can also be accessed from tablets along with laptops.

## Code


### Content
* **Angular-side** 
    The different components on the front-end side have been explained below:-
    * *Nav-bar* - This component is the navigation-bar of the entire application, consists of two options:-
        * TeMe - Home button
        * Vorlage - Button for template for service description
    * *Footer* - This component is the footer of the entire application.
    * *Search-bar* - This component consists of the 'TenderMe' heading along with the sub-heading in grey-color.
    * *Search-field* - This component consists of the search button along with the search-field and the question *'Was möchtest du beauftragen?'*.
    * *Search-results* - This component renders the search-results. At this point, it is hard-coded as the connection between front-end and back-end side has not established yet.
    * *pdf-render* - This component has been used to render the pdf viewer for the template service description
    * *test-mod* - This component is for testing and routing purpose.
    

* **Back-end side** 
    The backend consists of two parts:
    * *The ElasticSearch API* - After installing ElasticSearch locally, the way to access it, is through communicating with it as an API endpoint. In the *es-requests.txt* you will find most of the requests used in the App so far. You can find out more requests on the ElasticSearch website. The database or index could be then accessed on the front-end with Angular.
    * *Python for database creation* - We are using Python to automate inserting Tenders as PDFs in large quantities into the database. This includes converting the PDFs into Base64 code from a folder with all the tenders and sending them over the ElasticSearch API into the database or index.


### Requirements 

* **Angular-side** - Other than installing the packages (mentioned above in 'Installation' section), there are no additional requirements to run the code on front-end side.
* **Back-end side**- Other than installing the packages (mentioned above in 'Installation' section), there are no additional requirements to run the code on back-end side.

### Limitations

* The front-end and back-end sides are not yet connected.
* The search-query is being saved on front-end but not yet sent to backend.
* The search-result page is hard-coded and needs the results to be shown there as per the protoype design.