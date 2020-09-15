<template>
  <div>
    <section id="contact" class="contact-area ptb_100">
      <div class="container">
        <div class="row justify-content-between align-items-center">
          <div class="col-12 col-lg-5">
            <div class="section-heading text-center mb-3">
              <h2>Let's connect!</h2>
              <p class="d-none d-sm-block mt-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laborum obcaecati dignissimos quae quo ad iste ipsum officiis deleniti asperiores sit.</p>
              <p class="d-block d-sm-none mt-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laborum obcaecati.</p>
            </div>
            <div class="contact-us">
              <ul>
                <li class="contact-info color-1 bg-hover active hover-bottom text-center p-5 m-3">
                  <span><i class="fas fa-mobile-alt fa-3x"></i></span> <a class="d-block my-2" href="#"><h3>+89 (0) 2354 5470091</h3> </a>
                  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
                </li>
                <li class="contact-info color-3 bg-hover active hover-bottom text-center p-5 m-3">
                  <span><i class="fas fa-envelope-open-text fa-3x"></i></span> <a class="d-none d-sm-block my-2" href="#"><h3>mail@company.com</h3> </a> <a class="d-block d-sm-none my-2" href="#"><h3>mail@your company.com</h3> </a>
                  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit.</p>
                </li>
              </ul>
            </div>
          </div>
          <div class="col-12 col-lg-6 pt-4 pt-lg-0">
            <div class="contact-box text-center">
              <form id="contact-form" method="POST" action="https://theme-land.com/digimx/demo/../../../static/assets/php/mail.php">
                <div class="row">
                  <div class="col-12">
                    <div class="form-group"><input type="text" class="form-control" name="name" placeholder="Name" required="required" /></div>
                    <div class="form-group"><input type="text" class="form-control" name="name" placeholder="Company Name" required="required" /></div>
                    <div class="form-group"><input type="email" class="form-control" name="email" placeholder="Email" required="required" /></div>
                    <div class="form-group"><input type="text" class="form-control" name="subject" placeholder="Phone" required="required" /></div>
                  </div>
                  <div class="col-12">
                    <div class="form-group"><textarea class="form-control" name="message" placeholder="Message" required="required"></textarea></div>
                  </div>
                  <div class="col-12">
                    <button type="submit" class="btn btn-bordered active btn-block mt-3">
                      <span class="text-white pr-3"><i class="fas fa-paper-plane"></i></span>Send Message
                    </button>
                  </div>
                </div>
              </form>
              <p class="form-message"></p>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="section cta-area bg-overlay ptb_100">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-12 col-lg-10">
            <div class="section-heading text-center m-0">
              <h2 class="text-white">Looking for the best digital agency &amp; marketing solution?</h2>
              <p class="text-white d-none d-sm-block mt-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laborum obcaecati dignissimos quae quo ad iste ipsum officiis deleniti asperiores sit.</p>
              <p class="text-white d-block d-sm-none mt-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laborum obcaecati.</p>
              <a href="#" class="btn btn-bordered-white mt-4">Contact Us</a>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  mounted () {
    // :: 15.0 CONTACT FORM ACTIVE CODE
    // Get the form.
    var form = $('#contact-form')
    // Get the messages div.
    var formMessages = $('.form-message')
    // Set up an event listener for the contact form.
    $(form).submit(function (e) {
      // Stop the browser from submitting the form.
      e.preventDefault()
      // Serialize the form data.
      var formData = $(form).serialize()
      // Submit the form using AJAX.
      $.ajax({
        type: 'POST',
        url: $(form).attr('action'),
        data: formData
      }).done(function (response) {
        // Make sure that the formMessages div has the 'success' class.
        $(formMessages).removeClass('error')
        $(formMessages).addClass('success')

        // Set the message text.
        $(formMessages).text(response)

        // Clear the form.
        $('#contact-form input,#contact-form textarea').val('')
      }).fail(function (data) {
        // Make sure that the formMessages div has the 'error' class.
        $(formMessages).removeClass('success')
        $(formMessages).addClass('error')

        // Set the message text.
        if (data.responseText !== '') {
          $(formMessages).text(data.responseText)
        } else {
          $(formMessages).text('Oops! An error occured and your message could not be sent.')
        }
      })
    })
  }
}
</script>

<style>

</style>
