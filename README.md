function publish(API_KEY) {
  fetch("https://app.ayrshare.com/api/post", {
    method: "POST",
    headers: {
      "Content-Type": "application/json",
      Authorization: 'Bearer ${API_KEY}',
    },
    body: JSON.stringify({
      post: "Today is a great day! ",
      platforms: ["twitter", "facebook", "instagram", "linkedin", "reddit", "telegram"],
    }),
  });
}