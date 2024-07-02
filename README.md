# Blog-Hub

Blog-Hub is a modern, responsive web application designed to showcase blog posts with various categories and recent posts. Built using Next.js, Tailwind CSS, and GraphQL, Blog-Hub provides a seamless and interactive user experience. This project also includes a blog section where I document the development process and insights about this portfolio project.

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [API Integration](#api-integration)
- [About](#about)
- [Authors](#authors)

## Features

- **GraphQL Integration:** Efficient data fetching and management using GraphQL.
- **Next.js:** Server-side rendering for fast and SEO-friendly web pages.
- **Tailwind CSS:** Utility-first CSS framework for rapid UI development.
- **Categories and Recent Posts:** Organized content with easy navigation.
- **Responsive Design:** Optimized for various devices and screen sizes.
- **Navigation Bar:** Simple and intuitive navigation across different sections.
- **Blog Section:** A dedicated blog to write about the portfolio and project insights.

## Technologies Used

- **Next.js:** A React framework for server-side rendering and static site generation.
- **Tailwind CSS:** A utility-first CSS framework for creating custom designs without writing CSS.
- **GraphQL:** A query language for your API, providing a complete and understandable description of the data in your API.
- **Hygraph:** A GraphQL-based headless CMS to manage and fetch content.

## Installation

To get started with Blog-Hub, follow these steps:
1. Clone the repository:

   ```sh
   git clone https://github.com/K-Musty/Blog-Hub.git
   cd blog-hub
   
2. **Install Dependencies:**

   npm install

3. **Set up environment variables:**

   Create a .env.local file in the root of your project and add the following:

   env

   NEXT_PUBLIC_GRAPHCMS_ENDPOINT=your-graphcms-endpoint

4. **Run the development server:**

   npm run dev

   Open http://localhost:3000 with your browser to see the result.

## Usage
Fetching and Displaying Posts

    Recent Posts: Displays a list of the most recent posts.
    Categories: Organizes posts into different categories for easy navigation.
    Post Details: View the detailed content of each post by clicking on the post title.

###Navigation Bar

- The navigation bar allows users to easily navigate between the home page, categories, and the blog section.
Project Structure

## Project Structure

.
├── components
│   ├── CategoryList.js
│   ├── Navbar.js
│   ├── PostWidget.js
│   └── ...
├── pages
│   ├── index.js
│   ├── _app.js
│   ├── post
│   │   └── [slug].js
│   └── ...
├── styles
│   ├── globals.css
│   └── ...
├── services
│   ├── index.js
│   └── ...
└── ...


    components: Reusable UI components such as Navbar, PostWidget, etc.
    pages: Next.js pages including dynamic routing for posts.
    styles: Global and component-specific styles.
    services: Functions for fetching data from the GraphQL API.

## API Integration

Blog-Hub integrates with a GraphQL API provided by Hygraph to manage and fetch content.
Fetching Posts

Example of fetching recent posts:

js

import { gql, GraphQLClient } from 'graphql-request';

const graphqlAPI = process.env.NEXT_PUBLIC_GRAPHCMS_ENDPOINT;

export const getRecentPosts = async () => {
  const query = gql`
    query GetRecentPosts {
      posts(orderBy: createdAt_DESC, first: 5) {
        title
        slug
        createdAt
        featuredImage {
          url
        }
      }
    }
  `;

  const client = new GraphQLClient(graphqlAPI);
  const data = await client.request(query);
  return data.posts;
};

About

Blog-Hub was inspired by the need to create a modern and responsive blog platform that leverages the power of GraphQL, Next.js, and Tailwind CSS. This project was developed as a portfolio project for Alx School.

## Authors
- **Abdulrahman Kalli Mustapha** - [kmustapha9564@gmail.com](https://github.com/K-Musty) ~ [LinkedIn](https://www.linkedin.com/in/abdulrahmankallimustapha/) ~ [@KMusty_](https://twitter.com/KMusty_):
- **Saleh Aliyu** - [salehaliyu111@gmail.com](https://github.com/salsdev) ~  [LinkedIn](https://www.linkedin.com/in/saleh-aliyu/) ~  [@salehh_aliy](https://twitter.com/salehh_aliy):


### GitHub Repository

You can find the source code for this project in the GitHub repository:
[Github](https://github.com/K-Musty/Blog-Hub.git)
