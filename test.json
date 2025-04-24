import React, { useState } from "react";

export default function LaserSimulator() {
  const [machine, setMachine] = useState("picolo");
  const [power, setPower] = useState(50);
  const [pulse, setPulse] = useState(100);
  const [feedback, setFeedback] = useState("");
  const [infoVisible, setInfoVisible] = useState(false);

  const startTreatment = () => {
    if (power > 80 || pulse < 50) {
      setFeedback("⚠️ Warning: Unsafe settings. Please adjust parameters.");
    } else {
      setFeedback("✅ Treatment started successfully with current settings.");
    }
  };

  const treatmentInfo = {
    picolo: {
      faceArea: "Pigmentation, Freckles, Melasma, Age Spots, Skin Brightening",
      powerRange: "40% - 60% (Adjust depending on skin type and severity)",
      pulseRange: "80 - 120 ms",
      effects: "Improves skin tone, reduces pigmentation and melasma. Best results seen in 2-3 sessions.",
      care: "Avoid direct sunlight, apply sunscreen daily (SPF 50+), and use gentle skincare products. Redness/swelling may last up to 48 hours.",
      salesTips: "Emphasize its non-invasive nature and fast recovery time. Highlight effective melasma and pigmentation clearance."
    },
    proyellow: {
      faceArea: "Vascular lesions, Redness, Rosacea, Acne, Skin Rejuvenation",
      powerRange: "50% - 70% (Lower power for rosacea and sensitive skin)",
      pulseRange: "60 - 100 ms",
      effects: "Reduces inflammation and redness, treats active acne. Noticeable improvement within 3-5 sessions.",
      care: "No hot showers/saunas for 24 hours. Use calming skincare and avoid scrubs for 1 week.",
      salesTips: "Promote its effectiveness on red, inflamed skin and its ability to calm active acne gently."
    },
    sylfirmx: {
      faceArea: "Lifting, Firming, Acne Scars, Wrinkles, Skin Texture",
      powerRange: "60% - 80% (Higher power for lifting, moderate for scars)",
      pulseRange: "100 - 150 ms",
      effects: "Stimulates collagen and reduces wrinkles. Lifting effect and scar improvement after 4 sessions.",
      care: "Moisturize regularly. Avoid makeup and exfoliation for 3 days. Sun protection is crucial.",
      salesTips: "Market as a versatile treatment that lifts, tightens, and repairs damaged skin. Suitable for anti-aging and scar revision."
    }
  };

  const currentInfo = treatmentInfo[machine];

  // Placeholder images, replace these with actual before/after images
  const beforeAfterImage = '/path-to-image.jpg'; 

  return (
    <div className="min-h-screen bg-gray-100 p-6">
      <div className="max-w-xl mx-auto bg-white p-8 rounded-2xl shadow">
        <h1 className="text-2xl font-bold text-center mb-6">
          Elogio Asia Pte Ltd<br />
          Laser Training Simulator
        </h1>

        <div className="mb-4">
          <label className="font-semibold block mb-1">Select Machine:</label>
          <select
            className="w-full border px-4 py-2 rounded"
            value={machine}
            onChange={(e) => setMachine(e.target.value)}
          >
            <option value="picolo">PicoLO</option>
            <option value="proyellow">Pro Yellow</option>
            <option value="sylfirmx">Sylfirm X</option>
          </select>
        </div>

        <div className="mb-4">
          <label className="font-semibold block mb-1">
            Power Level: {power}%
          </label>
          <input
            type="range"
            min="0"
            max="100"
            value={power}
            onChange={(e) => setPower(Number(e.target.value))}
            className="w-full"
          />
        </div>

        <div className="mb-4">
          <label className="font-semibold block mb-1">
            Pulse Duration: {pulse} ms
          </label>
          <input
            type="range"
            min="10"
            max="200"
            value={pulse}
            onChange={(e) => setPulse(Number(e.target.value))}
            className="w-full"
          />
        </div>

        <div className="text-center mt-6">
          <button
            onClick={startTreatment}
            className="bg-blue-600 text-white px-6 py-2 rounded hover:bg-blue-700"
          >
            Start Treatment
          </button>
        </div>

        {feedback && (
          <div className="mt-4 text-center font-semibold text-red-600">
            {feedback}
          </div>
        )}

        <div className="text-center mt-6">
          <button
            onClick={() => setInfoVisible(!infoVisible)}
            className="text-sm underline text-blue-600 hover:text-blue-800"
          >
            {infoVisible ? "Hide Treatment Info" : "Show Treatment Info"}
          </button>
        </div>

        {infoVisible && (
          <div className="mt-4 bg-gray-50 p-4 rounded border text-sm space-y-2">
            <p><strong>Target Areas:</strong> {currentInfo.faceArea}</p>
            <p><strong>Recommended Power:</strong> {currentInfo.powerRange}</p>
            <p><strong>Recommended Pulse:</strong> {currentInfo.pulseRange}</p>
            <p><strong>Expected Results:</strong> {currentInfo.effects}</p>
            <p><strong>Post-Treatment Care:</strong> {currentInfo.care}</p>
            <p><strong>Sales Tips:</strong> {currentInfo.salesTips}</p>
          </div>
        )}

        {/* Before and After Image Gallery */}
        <div className="mt-6 text-center">
          <h2 className="text-xl font-bold">Before & After Results</h2>
          <div className="flex justify-center mt-4">
            <div className="mx-2">
              <h3>Before Treatment</h3>
              <img
                src={beforeAfterImage}
                alt="Before Treatment"
                className="w-40 h-40 object-cover rounded"
              />
            </div>
            <div className="mx-2">
              <h3>After Treatment</h3>
              <img
                src={beforeAfterImage}
                alt="After Treatment"
                className="w-40 h-40 object-cover rounded"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  );
}
