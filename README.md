import React from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { CalendarDays, Droplets, Moon, Smile } from "lucide-react";

export default function HealthHub() {
  return (
    <div className="min-h-screen bg-gradient-to-br from-indigo-100 to-white p-6">
      <h1 className="text-4xl font-bold text-center text-indigo-800 mb-6">
        HealthHub - Wellness Dashboard for Teens
      </h1>

      <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        {/* Mood Check-in */}
        <Card className="shadow-lg">
          <CardContent className="p-4">
            <div className="flex items-center gap-3 mb-2">
              <Smile className="text-yellow-500" />
              <h2 className="text-xl font-semibold">Mood Check-in</h2>
            </div>
            <p className="text-sm text-gray-600">How are you feeling today?</p>
            <div className="flex justify-between mt-3">
              {['😀','🙂','😐','😔','😢'].map((mood, idx) => (
                <Button key={idx} variant="outline">{mood}</Button>
              ))}
            </div>
          </CardContent>
        </Card>

        {/* Sleep Log */}
        <Card className="shadow-lg">
          <CardContent className="p-4">
            <div className="flex items-center gap-3 mb-2">
              <Moon className="text-purple-500" />
              <h2 className="text-xl font-semibold">Sleep Log</h2>
            </div>
            <p className="text-sm text-gray-600">Track how many hours you slept.</p>
            <input type="number" placeholder="e.g., 7.5" className="mt-3 w-full p-2 border rounded" />
          </CardContent>
        </Card>

        {/* Water Tracker */}
        <Card className="shadow-lg">
          <CardContent className="p-4">
            <div className="flex items-center gap-3 mb-2">
              <Droplets className="text-blue-500" />
              <h2 className="text-xl font-semibold">Water Tracker</h2>
            </div>
            <p className="text-sm text-gray-600">Glasses of water today</p>
            <div className="grid grid-cols-4 gap-2 mt-3">
              {Array.from({ length: 8 }).map((_, idx) => (
                <Button key={idx} variant="outline">{idx + 1}</Button>
              ))}
            </div>
          </CardContent>
        </Card>

        {/* Daily Check-in Calendar */}
        <Card className="shadow-lg col-span-1 md:col-span-2">
          <CardContent className="p-4">
            <div className="flex items-center gap-3 mb-2">
              <CalendarDays className="text-green-500" />
              <h2 className="text-xl font-semibold">Daily Check-ins</h2>
            </div>
            <p className="text-sm text-gray-600">Coming soon: calendar view with mood & sleep logs.</p>
            <div className="mt-4 text-center text-gray-400 italic">(Calendar component placeholder)</div>
          </CardContent>
        </Card>
      </div>
    </div>
  );
}
