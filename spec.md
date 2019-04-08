---
title:           description: 'The server can not complete the request'
language_tabs:
toc_footers: []
includes: []
search: true
highlight_theme: darkula
---








































        - SharedHosts
      responses:
        200:
          $ref: '#/components/responses/SharedHostsResponse'
        400:
          description: 'The request could not be fulfilled due to bad syntax'
        404:
          description: 'The server could not find the data requested'
        418:
          description: 'I am a teapot'
        500:
          description: 'The server can not complete the request'
  /hosts/managed:
    get:
      summary: A list of resources that are considered managed hosts.
      description: A non-paginated list of resources that are considered managed hosts.
      operationId: getManagedHosts
      tags:
        - ManagedHosts
      responses:
        200:
          $ref: '#/components/responses/ManagedHostsResponse'
        400:
          description: 'The request could not be fulfilled due to bad syntax'
        404:
          description: 'The server could not find the data requested'
        418:
          description: 'I am a teapot'
        500:
          description: 'The server can not complete the request'

> openapi: "3.0.1"

> info:

>   title: "PHPVersions API"

>   description: An api that centers around hosts and what versions of PHP they support. This API details managed hosts, shared hosts, operating systems as well as detailing CVE's against PHP.

>   version: "0.9.0"

>   contact:

>     name: Developer Support

>     url: phpversions.io/support

>     email: support@phpversions.io

>   license:

>     name: MIT

>     url: https://opensource.org/licenses/MIT

> servers:

> - url: https://phpversions.org/api

>   description: Production Server

> - url: http://localhost/api

>   description: Local Server

> tags:

>   - name: ManagedHosts

>     description: Grouping for any resources considered a managed host; when you do not have control over the server.

>   - name: SharedHosts

>     description: Grouping for any resources considered a shared host; when a host will put multiple projects, sites, and customers on a single server.

>   - name: PaasHosts

>     description: Grouping for any resources considered a Paas host; essentially a service where a user pushes up code and the host has servers configured and ready to go.

>   - name: OperatingSystems

>     description: Grouping for resources considered an operating system; examples like MacOS, Arch Linux, Ubuntu and more.

>   - name: Vulnerabilities

>     description: Grouping for resources that are listed on the CVE list for PHP.

>   - name: CurrentVersion

>     description: Grouping for resources that support the current version of PHP.

>   - name: Contributors

>     description: Grouping for resources that support contributors to the project on Github.

> paths:

>   /hosts/shared:

>     get:

>       summary: A list of resources that are considered shared hosts.

>       description: A non-paginated list of resources that are considered shared hosts.

>       operationId: getSharedHosts

>       tags:

components:
  responses:
    SharedHostsResponse:
      description: A list a resorts at Walt Disney World
        content:
          application/json:
            schema:
              type: object
              properties:
                data:
                  type: array
                  items:
                    $ref: '#/components/schemas/Resorts'
            examples:
              sharedHostsResponse:
                $ref: '#/components/examples/SharedHostsResponse'