DocumentJS
==========

Generate and control your web application interface with DocumentJS.

Syntax
======

Create a `document object` for your app, to act as your front end control center. All html tags and attributes are supported as objects, and the functionality works precisely as you'd expect it to. Because Air JS prototyping supports the Observer Pattern, any changes made to the objects owned by `document` will reflect on the page:

    Document = new document({

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
    
You can build different models for the page and call them neatly wighin the Document object, or traverse through them as the user interacts with the page.

    Models.ChatRoom = new model({

        chat_wrapper: new div({

            class: "chat_wrapper",
            // design in progress

        }),

        chat_ad: new html("<embed code>");

    });
    
The `model object` simply acts as a container for elements and returns itself in html form through its method `html`.

    Document.body.AppBody.ChatRoomWrapper = {
    
      new div({
      
        class : "ChatRoomWrapper",
        ChatRoom : new html(Models.ChatRoom)
      
      })
    
    }
    
