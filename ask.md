
# how to refund razor pay money

for refound monay there are api by that we can refund money

      import razorpay
      client = razorpay.Client(auth=("YOUR_ID", "YOUR_SECRET"))

      client.payment.refund(paymentId,{
        "amount": "100",
        "speed": "normal",
        "notes": {
          "notes_key_1": "Beam me up Scotty.",
          "notes_key_2": "Engage"
        },
        "receipt": "Receipt No. 31"
      })
      
 
