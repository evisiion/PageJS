Introduction to PageJS
======================

Generate and control your web application interface with PageJS. This very lightweight interface framework allows developers to:

- Build and generate any webpage with JavaScript.
- Store HTML in JSON structure, for easy access.
- Manipulate page structure quickly and dramatically.
- Store page sections as Models for later use.

PageJS's Easy-learn Syntax
==========================

Create a `PageJS object` for your app, to act as your front end control center. All html tags are supported as objects, and attributes for each tag objet are supported as proprties. Because PageJS utilized the Observer Pattern, any changes made to the objects owned by `PageJS` will reflect on the page in real-time, with no further action. 

To get started, simply create an index.html page with nothing on it except script links to PageJS and your PageJS script.

Index.html:

    <script src="Page.JS"></script>
    <script src="MyPage.JS"></script>

MyPage.js:

    Page = new PageJS({

        Head: new head({

            title: new title({
            
            	text: "My First DocumentJS Interface"
            
            }),
            description: new description({
            
            	text: "This page is generated and manipulated dynamically via DocumentJS."
            
            }),
            favicon: new link({

                rel: "icon",
                type: "image/png",
                href: "link.icon"

            }),
            style: new link({

                rel: "stylesheet",
                type: "text/css",
                href: "link.css"

            })

        }),

        Body: new body({

            header: new div({

                class: "header",
                    logo: new div({

                        class: "logo",
                        text: "Logo Text",
                        style: "color: gray"

                    })


            }),
            AppBody: new div({

                class: "app_body",
                image_gallery: new html("modules/gallery.html"),


            }),
            footer: new div({

                title: new h1({

                    class: "map_title",
                    text: "Google Map",
                    style: "color:gray"

                }),
                google_map: new html("<embed code>")

            })

        })

    });
    
Organize Interfaces into Models with PageJS
===========================================
    
You can build different models for the page and call them neatly wighin the `PageJS object`, or traverse through them as the user interacts with the page.

    Models.ChatRoom = new model({

        chat_wrapper: new div({

            class: "chat_wrapper",
            // design in progress

        }),

        chat_ad: new html("<embed code>");

    });
    
The `model object` simply acts as a container for elements and returns itself in html form.

    Page.body.AppBody.ChatRoomWrapper = {
    
      new div({
      
        class : "ChatRoomWrapper",
        ChatRoom : new html(Models.ChatRoom)
      
      })
    
    }

