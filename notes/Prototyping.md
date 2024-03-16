# Prototyping and the role of the Designer

## Customer Journeys

Outlining the constraints of the problem and the solution

```ts
interface CustomerJourneyStep {
    stepName: string;
    description: string;
    touchpoints: string[];
    emotions: string[];
    actions: string[];
    challenges: string[];
}

const customerJourneySteps: CustomerJourneyStep[] = [
    {
        stepName: "Awareness",
        description: "Introducing the product to potential customers",
        touchpoints: ["Social media ads", "Website landing page"],
        emotions: ["Curiosity", "Interest"],
        actions: ["Viewing ad content", "Visiting website"],
        challenges: ["Standing out among competitors", "Capturing attention quickly"]
    },
    {
        stepName: "Consideration",
        description: "Evaluating the product before making a purchase decision",
        touchpoints: ["Product reviews", "Comparison websites"],
        emotions: ["Confusion", "Excitement"],
        actions: ["Reading reviews", "Comparing features"],
        challenges: ["Addressing concerns", "Providing clear information"]
    },
    {
        stepName: "Decision Making",
        description: "Making the final choice to purchase the product",
        touchpoints: ["Trial offers", "Customer testimonials"],
        emotions: ["Anticipation", "Apprehension"],
        actions: ["Trying demo versions", "Seeking recommendations"],
        challenges: ["Overcoming objections", "Building trust"]
    },
    {
        stepName: "Purchase",
        description: "Completing the transaction and acquiring the product",
        touchpoints: ["Checkout process", "Payment confirmation"],
        emotions: ["Satisfaction", "Relief"],
        actions: ["Adding to cart", "Entering payment details"],
        challenges: ["Smooth payment processing", "Security concerns"]
    },
    {
        stepName: "Delivery",
        description: "Receiving and getting familiar with the purchased product",
        touchpoints: ["Shipping notifications", "Unboxing experience"],
        emotions: ["Excitement", "Impatience"],
        actions: ["Tracking shipment", "Inspecting product"],
        challenges: ["Timely delivery", "Product quality"]
    },
    {
        stepName: "Usage",
        description: "Using the product as intended for its intended purpose",
        touchpoints: ["User manuals", "Customer support"],
        emotions: ["Satisfaction", "Frustration"],
        actions: ["Learning features", "Troubleshooting issues"],
        challenges: ["User adoption", "Technical difficulties"]
    },
    {
      stepName:"Loyalty and Advocacy",
      description:"Building long-term relationships and turning customers into advocates",
      touchpoints:["Rewards programs","Referral incentives"],
      emotions:["Gratitude","Enthusiasm"],
      actions:["Participating in loyalty programs","Referring friends"],
      challenges:["Maintaining interest","Competing loyalty programs"]
  }
];
```

## Sketches

Giving a shape to ideas and concepts

## The role of the Designer

The role of the designer is to bridge the gap between the customer and the developer.

## Tools

A Simple pen and paper is enough, no need to be fancy.
