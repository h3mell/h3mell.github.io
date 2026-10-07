/* =====================================================
   PERSONAL WEBSITE JAVASCRIPT

   This file controls:

   1. Mobile navigation
   2. Current year
   3. Gallery filtering
   4. Gallery lightbox
   5. Blog modal
   6. Contact form demonstration
===================================================== */


/* =====================================================
   MOBILE NAVIGATION
===================================================== */

const menuToggle = document.querySelector(".menu-toggle");
const navLinks = document.querySelector(".nav-links");


if (menuToggle && navLinks) {

    menuToggle.addEventListener("click", () => {

        const isOpen =
            navLinks.classList.toggle("open");

        menuToggle.setAttribute(
            "aria-expanded",
            isOpen
        );

    });


    // Close mobile menu after clicking a link

    navLinks.querySelectorAll("a").forEach(link => {

        link.addEventListener("click", () => {

            navLinks.classList.remove("open");

            menuToggle.setAttribute(
                "aria-expanded",
                "false"
            );

        });

    });

}


/* =====================================================
   CURRENT YEAR
===================================================== */

const yearElements =
    document.querySelectorAll("#year");


yearElements.forEach(element => {

    element.textContent =
        new Date().getFullYear();

});


/* =====================================================
   GALLERY FILTER
===================================================== */

const filterButtons =
    document.querySelectorAll(".filter-btn");

const galleryItems =
    document.querySelectorAll(".gallery-item");


filterButtons.forEach(button => {

    button.addEventListener("click", () => {

        /* Remove active state */

        filterButtons.forEach(btn => {

            btn.classList.remove("active");

        });


        /* Activate clicked button */

        button.classList.add("active");


        /* Get selected category */

        const filter =
            button.dataset.filter;


        galleryItems.forEach(item => {

            const category =
                item.dataset.category;


            if (
                filter === "all" ||
                category === filter
            ) {

                item.style.display = "";

                /* Small animation */

                item.animate(
                    [
                        {
                            opacity: 0,
                            transform: "scale(0.95)"
                        },
                        {
                            opacity: 1,
                            transform: "scale(1)"
                        }
                    ],
                    {
                        duration: 300,
                        easing: "ease"
                    }
                );

            } else {

                item.style.display = "none";

            }

        });

    });

});


/* =====================================================
   GALLERY LIGHTBOX
===================================================== */

const lightbox =
    document.querySelector("#lightbox");

const lightboxImage =
    document.querySelector("#lightbox-image");

const lightboxClose =
    document.querySelector(".lightbox-close");


if (lightbox) {

    galleryItems.forEach(item => {

        item.addEventListener("click", () => {

            const image =
                item.querySelector("img");


            if (!image) return;


            lightboxImage.src =
                image.src;

            lightboxImage.alt =
                image.alt;


            lightbox.classList.add("active");

            document.body.style.overflow =
                "hidden";

        });

    });


    function closeLightbox() {

        lightbox.classList.remove("active");

        document.body.style.overflow =
            "";

    }


    if (lightboxClose) {

        lightboxClose.addEventListener(
            "click",
            closeLightbox
        );

    }


    lightbox.addEventListener(
        "click",
        event => {

            if (event.target === lightbox) {

                closeLightbox();

            }

        }
    );

}


/* =====================================================
   BLOG POSTS
===================================================== */


/*
   You can edit your blog posts here.

   Each post contains:

   title
   date
   content
*/

const blogPosts = {

    post1: {

        title:
            "Why I Started Creating Again",

        date:
            "October 1, 2026",

        content: `

            <p>
                There is something special about creating
                something from nothing. It doesn't have to
                be perfect. It simply has to exist.
            </p>

            <p>
                For a while, I found myself consuming more
                content than I was creating. I decided to
                change that by making time for small creative
                projects again.
            </p>

            <p>
                The goal isn't perfection. The goal is to
                experiment, learn, and keep moving forward.
            </p>

        `

    },


    post2: {

        title:
            "Learning One Step at a Time",

        date:
            "September 18, 2026",

        content: `

            <p>
                Learning something new can feel overwhelming
                when you look at everything you don't know.
            </p>

            <p>
                One thing that has helped me is breaking
                large goals into very small steps.
            </p>

            <p>
                Instead of asking how I can master something,
                I ask what I can understand today.
            </p>

        `

    },


    post3: {

        title:
            "Building a Better Workspace",

        date:
            "August 30, 2026",

        content: `

            <p>
                Your environment can have a surprising
                effect on how you think and work.
            </p>

            <p>
                A comfortable chair, good lighting, a clean
                desk, and fewer distractions can make it
                much easier to focus.
            </p>

            <p>
                You don't need an expensive setup.
                You simply need a space that makes it easier
                for you to do your best work.
            </p>

        `

    },


    post4: {

        title:
            "Finding Inspiration Everywhere",

        date:
            "August 12, 2026",

        content: `

            <p>
                Inspiration doesn't always come from books,
                galleries, or websites.
            </p>

            <p>
                It can come from a conversation, a walk,
                a building, a photograph, or even an
                ordinary moment.
            </p>

            <p>
                Paying attention is often the first step
                toward finding interesting ideas.
            </p>

        `

    }

};


/* =====================================================
   BLOG MODAL
===================================================== */

const blogModal =
    document.querySelector("#blog-modal");

const modalTitle =
    document.querySelector("#modal-title");

const modalDate =
    document.querySelector("#modal-date");

const modalBody =
    document.querySelector("#modal-body");

const modalClose =
    document.querySelector(".modal-close");

const readMoreButtons =
    document.querySelectorAll(".read-more");


if (
    blogModal &&
    modalTitle &&
    modalDate &&
    modalBody
) {

    readMoreButtons.forEach(button => {

        button.addEventListener(
            "click",
            () => {

                const postId =
                    button.dataset.post;

                const post =
                    blogPosts[postId];


                if (!post) return;


                modalTitle.textContent =
                    post.title;

                modalDate.textContent =
                    post.date;

                modalBody.innerHTML =
                    post.content;


                blogModal.classList.add(
                    "active"
                );

                document.body.style.overflow =
                    "hidden";

            }
        );

    });


    function closeBlogModal() {

        blogModal.classList.remove(
            "active"
        );

        document.body.style.overflow =
            "";

    }


    if (modalClose) {

        modalClose.addEventListener(
            "click",
            closeBlogModal
        );

    }


    blogModal.addEventListener(
        "click",
        event => {

            if (
                event.target === blogModal
            ) {

                closeBlogModal();

            }

        }
    );

}


/* =====================================================
   ESC KEY
===================================================== */

document.addEventListener(
    "keydown",
    event => {

        if (event.key !== "Escape") {
            return;
        }


        /* Close lightbox */

        if (
            lightbox &&
            lightbox.classList.contains("active")
        ) {

            lightbox.classList.remove(
                "active"
            );

            document.body.style.overflow =
                "";

        }


        /* Close blog modal */

        if (
            blogModal &&
            blogModal.classList.contains("active")
        ) {

            blogModal.classList.remove(
                "active"
            );

            document.body.style.overflow =
                "";

        }

    }
);


/* =====================================================
   CONTACT FORM
===================================================== */


/*
   This currently prevents the page from refreshing.

   To actually receive messages, connect the form
   to a backend or service such as Formspree.
*/

const contactForm =
    document.querySelector(".contact-form");


if (contactForm) {

    contactForm.addEventListener(
        "submit",
        event => {

            event.preventDefault();


            alert(
                "Thanks! Your message form is working. Connect this form to a backend or form service to receive submissions."
            );


            contactForm.reset();

        }
    );

}