import React, { useState } from 'react';
import { Search, MapPin, Star, Activity, User, Package } from 'lucide-react';
import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

const HospitalPlatform = () => {
  const [searchTerm, setSearchTerm] = useState('');
  
  const hospitals = [
    {
      id: 1,
      name: "Kenyatta National Hospital",
      type: "Public",
      location: "Nairobi",
      rating: 4.2,
      doctors: 350,
      specialties: ["Surgery", "Oncology", "Pediatrics"],
      equipment: ["MRI", "CT Scan", "X-Ray"],
      medicines: "Well Stocked",
    },
    {
      id: 2,
      name: "Aga Khan University Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.5,
      doctors: 200,
      specialties: ["Cardiology", "Neurology", "Orthopedics"],
      equipment: ["MRI", "CT Scan", "Ultrasound"],
      medicines: "Fully Stocked",
    },
    {
      id: 3,
      name: "Moi Teaching & Referral Hospital",
      type: "Public",
      location: "Eldoret",
      rating: 4.0,
      doctors: 250,
      specialties: ["General Medicine", "Surgery", "Obstetrics"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Well Stocked",
    },
    {
      id: 4,
      name: "Nairobi Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.6,
      doctors: 180,
      specialties: ["Cardiology", "Oncology", "Pediatrics"],
      equipment: ["MRI", "CT Scan", "PET Scan"],
      medicines: "Fully Stocked",
    },
    {
      id: 5,
      name: "Coast General Hospital",
      type: "Public",
      location: "Mombasa",
      rating: 3.8,
      doctors: 150,
      specialties: ["General Medicine", "Surgery", "Emergency Care"],
      equipment: ["X-Ray", "CT Scan", "Ultrasound"],
      medicines: "Well Stocked",
    },
    {
      id: 6,
      name: "Gertrude's Children's Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.4,
      doctors: 90,
      specialties: ["Pediatrics", "Child Surgery", "Vaccination"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Fully Stocked",
    },
    {
      id: 7,
      name: "Kisumu County Referral Hospital",
      type: "Public",
      location: "Kisumu",
      rating: 3.9,
      doctors: 120,
      specialties: ["General Medicine", "Maternity", "HIV Care"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    },
    {
      id: 8,
      name: "MP Shah Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.3,
      doctors: 150,
      specialties: ["Surgery", "Internal Medicine", "Dermatology"],
      equipment: ["MRI", "CT Scan", "Mammography"],
      medicines: "Fully Stocked",
    },
    {
      id: 9,
      name: "Nakuru Level 5 Hospital",
      type: "Public",
      location: "Nakuru",
      rating: 3.7,
      doctors: 100,
      specialties: ["General Medicine", "Emergency Care", "Obstetrics"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Well Stocked",
    },
    {
      id: 10,
      name: "Karen Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.4,
      doctors: 120,
      specialties: ["Cardiology", "Neurology", "Orthopedics"],
      equipment: ["MRI", "CT Scan", "Cardiac Cath Lab"],
      medicines: "Fully Stocked",
    },
    {
      id: 11,
      name: "Machakos Level 5 Hospital",
      type: "Public",
      location: "Machakos",
      rating: 3.8,
      doctors: 90,
      specialties: ["General Medicine", "Surgery", "Pediatrics"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    },
    {
      id: 12,
      name: "Coptic Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.1,
      doctors: 80,
      specialties: ["General Medicine", "Surgery", "Dental Care"],
      equipment: ["X-Ray", "CT Scan", "Dental Equipment"],
      medicines: "Well Stocked",
    },
    {
      id: 13,
      name: "Nyeri County Referral Hospital",
      type: "Public",
      location: "Nyeri",
      rating: 3.6,
      doctors: 85,
      specialties: ["General Medicine", "Maternity", "Emergency Care"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Moderately Stocked",
    },
    {
      id: 14,
      name: "Avenue Hospital",
      type: "Private",
      location: "Kisumu",
      rating: 4.2,
      doctors: 70,
      specialties: ["Surgery", "Pediatrics", "Obstetrics"],
      equipment: ["MRI", "CT Scan", "Ultrasound"],
      medicines: "Fully Stocked",
    },
    {
      id: 15,
      name: "Kakamega County Referral Hospital",
      type: "Public",
      location: "Kakamega",
      rating: 3.7,
      doctors: 95,
      specialties: ["General Medicine", "Surgery", "HIV Care"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Well Stocked",
    },
    {
      id: 16,
      name: "Mater Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.3,
      doctors: 130,
      specialties: ["Cardiology", "Oncology", "Neurology"],
      equipment: ["MRI", "CT Scan", "Cardiac Cath Lab"],
      medicines: "Fully Stocked",
    },
    {
      id: 17,
      name: "Embu Level 5 Hospital",
      type: "Public",
      location: "Embu",
      rating: 3.8,
      doctors: 80,
      specialties: ["General Medicine", "Surgery", "Pediatrics"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Moderately Stocked",
    },
    {
      id: 18,
      name: "Pandya Memorial Hospital",
      type: "Private",
      location: "Mombasa",
      rating: 4.1,
      doctors: 90,
      specialties: ["Surgery", "Internal Medicine", "Cardiology"],
      equipment: ["MRI", "CT Scan", "Ultrasound"],
      medicines: "Well Stocked",
    },
    {
      id: 19,
      name: "Garissa County Referral Hospital",
      type: "Public",
      location: "Garissa",
      rating: 3.5,
      doctors: 60,
      specialties: ["General Medicine", "Emergency Care", "Maternity"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    },
    {
      id: 20,
      name: "Nairobi Women's Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.2,
      doctors: 100,
      specialties: ["Obstetrics", "Gynecology", "Pediatrics"],
      equipment: ["MRI", "Ultrasound", "Mammography"],
      medicines: "Fully Stocked",
    },
    {
      id: 21,
      name: "Kericho County Referral Hospital",
      type: "Public",
      location: "Kericho",
      rating: 3.7,
      doctors: 75,
      specialties: ["General Medicine", "Surgery", "HIV Care"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Well Stocked",
    },
    {
      id: 22,
      name: "Outspan Hospital",
      type: "Private",
      location: "Nyeri",
      rating: 4.0,
      doctors: 65,
      specialties: ["Internal Medicine", "Surgery", "Pediatrics"],
      equipment: ["CT Scan", "Ultrasound", "X-Ray"],
      medicines: "Well Stocked",
    },
    {
      id: 23,
      name: "Mama Lucy Kibaki Hospital",
      type: "Public",
      location: "Nairobi",
      rating: 3.8,
      doctors: 85,
      specialties: ["General Medicine", "Maternity", "Emergency Care"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    }
  ];

  const filteredHospitals = hospitals.filter(hospital =>
    hospital.name.toLowerCase().includes(searchTerm.toLowerCase()) ||
    hospital.location.toLowerCase().includes(searchTerm.toLowerCase())
  );

  return (
    <div className="min-h-screen bg-gray-50 p-8">
      {/* Header */}
      <div className="max-w-6xl mx-auto">
        <h1 className="text-4xl font-bold text-center mb-2">Kenya Hospital Services Directory</h1>
        <p className="text-gray-600 text-center mb-8">Find and compare healthcare facilities across Kenya</p>
        
        {/* Search Bar */}
        <div className="relative mb-8">
          <input
            type="text"
            placeholder="Search hospitals by name or location..."
            className="w-full p-4 rounded-lg border shadow-sm focus:ring-2 focus:ring-blue-500"
            value={searchTerm}
            onChange={(e) => setSearchTerm(e.target.value)}
          />
          <Search className="absolute right-4 top-4 text-gray-400" />
        </div>

        {/* Hospital Cards */}
        <div className="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
          {filteredHospitals.map(hospital => (
            <Card key={hospital.id} className="hover:shadow-lg transition-shadow">
              <CardHeader>
                <CardTitle className="flex items-center justify-between">
                  <span>{hospital.name}</span>
                  <span className="text-sm px-2 py-1 bg-blue-100 text-blue-800 rounded">
                    {hospital.type}
                  </span>
                </CardTitle>
                <CardDescription className="flex items-center gap-1">
                  <MapPin className="w-4 h-4" />
                  {hospital.location}
                </CardDescription>
              </CardHeader>
              <CardContent>
                <div className="space-y-4">
                  <div className="flex items-center gap-2">
                    <Star className="w-5 h-5 text-yellow-500" />
                    <span>{hospital.rating} / 5.0 Rating</span>
                  </div>
                  
                  <div className="flex items-center gap-2">
                    <User className="w-5 h-5 text-blue-500" />
                    <span>{hospital.doctors} Doctors</span>
                  </div>
                  
                  <div className="flex items-center gap-2">
                    <Activity className="w-5 h-5 text-green-500" />
                    <span>Specialties: {hospital.specialties.join(", ")}</span>
                  </div>
                  
                  <div className="flex items-center gap-2">
                    <Package className="w-5 h-5 text-purple-500" />
                    <span>Medicine Status: {hospital.medicines}</span>
                  </div>
                  
                  <button className="w-full mt-4 bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700 transition-colors">
                    View Details
                  </button>
                </div>
              </CardContent>
            </Card>
          ))}
        </div>
      </div>
    </div>
  );
};

export default HospitalPlatform;import React, { useState } from 'react';
import { Search, MapPin, Star, Activity, User, Package } from 'lucide-react';
import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

const HospitalPlatform = () => {
  const [searchTerm, setSearchTerm] = useState('');
  
  const hospitals = [
    {
      id: 1,
      name: "Kenyatta National Hospital",
      type: "Public",
      location: "Nairobi",
      rating: 4.2,
      doctors: 350,
      specialties: ["Surgery", "Oncology", "Pediatrics"],
      equipment: ["MRI", "CT Scan", "X-Ray"],
      medicines: "Well Stocked",
    },
    {
      id: 2,
      name: "Aga Khan University Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.5,
      doctors: 200,
      specialties: ["Cardiology", "Neurology", "Orthopedics"],
      equipment: ["MRI", "CT Scan", "Ultrasound"],
      medicines: "Fully Stocked",
    },
    {
      id: 3,
      name: "Moi Teaching & Referral Hospital",
      type: "Public",
      location: "Eldoret",
      rating: 4.0,
      doctors: 250,
      specialties: ["General Medicine", "Surgery", "Obstetrics"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Well Stocked",
    },
    {
      id: 4,
      name: "Nairobi Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.6,
      doctors: 180,
      specialties: ["Cardiology", "Oncology", "Pediatrics"],
      equipment: ["MRI", "CT Scan", "PET Scan"],
      medicines: "Fully Stocked",
    },
    {
      id: 5,
      name: "Coast General Hospital",
      type: "Public",
      location: "Mombasa",
      rating: 3.8,
      doctors: 150,
      specialties: ["General Medicine", "Surgery", "Emergency Care"],
      equipment: ["X-Ray", "CT Scan", "Ultrasound"],
      medicines: "Well Stocked",
    },
    {
      id: 6,
      name: "Gertrude's Children's Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.4,
      doctors: 90,
      specialties: ["Pediatrics", "Child Surgery", "Vaccination"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Fully Stocked",
    },
    {
      id: 7,
      name: "Kisumu County Referral Hospital",
      type: "Public",
      location: "Kisumu",
      rating: 3.9,
      doctors: 120,
      specialties: ["General Medicine", "Maternity", "HIV Care"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    },
    {
      id: 8,
      name: "MP Shah Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.3,
      doctors: 150,
      specialties: ["Surgery", "Internal Medicine", "Dermatology"],
      equipment: ["MRI", "CT Scan", "Mammography"],
      medicines: "Fully Stocked",
    },
    {
      id: 9,
      name: "Nakuru Level 5 Hospital",
      type: "Public",
      location: "Nakuru",
      rating: 3.7,
      doctors: 100,
      specialties: ["General Medicine", "Emergency Care", "Obstetrics"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Well Stocked",
    },
    {
      id: 10,
      name: "Karen Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.4,
      doctors: 120,
      specialties: ["Cardiology", "Neurology", "Orthopedics"],
      equipment: ["MRI", "CT Scan", "Cardiac Cath Lab"],
      medicines: "Fully Stocked",
    },
    {
      id: 11,
      name: "Machakos Level 5 Hospital",
      type: "Public",
      location: "Machakos",
      rating: 3.8,
      doctors: 90,
      specialties: ["General Medicine", "Surgery", "Pediatrics"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    },
    {
      id: 12,
      name: "Coptic Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.1,
      doctors: 80,
      specialties: ["General Medicine", "Surgery", "Dental Care"],
      equipment: ["X-Ray", "CT Scan", "Dental Equipment"],
      medicines: "Well Stocked",
    },
    {
      id: 13,
      name: "Nyeri County Referral Hospital",
      type: "Public",
      location: "Nyeri",
      rating: 3.6,
      doctors: 85,
      specialties: ["General Medicine", "Maternity", "Emergency Care"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Moderately Stocked",
    },
    {
      id: 14,
      name: "Avenue Hospital",
      type: "Private",
      location: "Kisumu",
      rating: 4.2,
      doctors: 70,
      specialties: ["Surgery", "Pediatrics", "Obstetrics"],
      equipment: ["MRI", "CT Scan", "Ultrasound"],
      medicines: "Fully Stocked",
    },
    {
      id: 15,
      name: "Kakamega County Referral Hospital",
      type: "Public",
      location: "Kakamega",
      rating: 3.7,
      doctors: 95,
      specialties: ["General Medicine", "Surgery", "HIV Care"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Well Stocked",
    },
    {
      id: 16,
      name: "Mater Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.3,
      doctors: 130,
      specialties: ["Cardiology", "Oncology", "Neurology"],
      equipment: ["MRI", "CT Scan", "Cardiac Cath Lab"],
      medicines: "Fully Stocked",
    },
    {
      id: 17,
      name: "Embu Level 5 Hospital",
      type: "Public",
      location: "Embu",
      rating: 3.8,
      doctors: 80,
      specialties: ["General Medicine", "Surgery", "Pediatrics"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Moderately Stocked",
    },
    {
      id: 18,
      name: "Pandya Memorial Hospital",
      type: "Private",
      location: "Mombasa",
      rating: 4.1,
      doctors: 90,
      specialties: ["Surgery", "Internal Medicine", "Cardiology"],
      equipment: ["MRI", "CT Scan", "Ultrasound"],
      medicines: "Well Stocked",
    },
    {
      id: 19,
      name: "Garissa County Referral Hospital",
      type: "Public",
      location: "Garissa",
      rating: 3.5,
      doctors: 60,
      specialties: ["General Medicine", "Emergency Care", "Maternity"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    },
    {
      id: 20,
      name: "Nairobi Women's Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.2,
      doctors: 100,
      specialties: ["Obstetrics", "Gynecology", "Pediatrics"],
      equipment: ["MRI", "Ultrasound", "Mammography"],
      medicines: "Fully Stocked",
    },
    {
      id: 21,
      name: "Kericho County Referral Hospital",
      type: "Public",
      location: "Kericho",
      rating: 3.7,
      doctors: 75,
      specialties: ["General Medicine", "Surgery", "HIV Care"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Well Stocked",
    },
    {
      id: 22,
      name: "Outspan Hospital",
      type: "Private",
      location: "Nyeri",
      rating: 4.0,
      doctors: 65,
      specialties: ["Internal Medicine", "Surgery", "Pediatrics"],
      equipment: ["CT Scan", "Ultrasound", "X-Ray"],
      medicines: "Well Stocked",
    },
    {
      id: 23,
      name: "Mama Lucy Kibaki Hospital",
      type: "Public",
      location: "Nairobi",
      rating: 3.8,
      doctors: 85,
      specialties: ["General Medicine", "Maternity", "Emergency Care"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    }
  ];

  const filteredHospitals = hospitals.filter(hospital =>
    hospital.name.toLowerCase().includes(searchTerm.toLowerCase()) ||
    hospital.location.toLowerCase().includes(searchTerm.toLowerCase())
  );

  return (
    <div className="min-h-screen bg-gray-50 p-8">
      {/* Header */}
      <div className="max-w-6xl mx-auto">
        <h1 className="text-4xl font-bold text-center mb-2">Kenya Hospital Services Directory</h1>
        <p className="text-gray-600 text-center mb-8">Find and compare healthcare facilities across Kenya</p>
        
        {/* Search Bar */}
        <div className="relative mb-8">
          <input
            type="text"
            placeholder="Search hospitals by name or location..."
            className="w-full p-4 rounded-lg border shadow-sm focus:ring-2 focus:ring-blue-500"
            value={searchTerm}
            onChange={(e) => setSearchTerm(e.target.value)}
          />
          <Search className="absolute right-4 top-4 text-gray-400" />
        </div>

        {/* Hospital Cards */}
        <div className="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
          {filteredHospitals.map(hospital => (
            <Card key={hospital.id} className="hover:shadow-lg transition-shadow">
              <CardHeader>
                <CardTitle className="flex items-center justify-between">
                  <span>{hospital.name}</span>
                  <span className="text-sm px-2 py-1 bg-blue-100 text-blue-800 rounded">
                    {hospital.type}
                  </span>
                </CardTitle>
                <CardDescription className="flex items-center gap-1">
                  <MapPin className="w-4 h-4" />
                  {hospital.location}
                </CardDescription>
              </CardHeader>
              <CardContent>
                <div className="space-y-4">
                  <div className="flex items-center gap-2">
                    <Star className="w-5 h-5 text-yellow-500" />
                    <span>{hospital.rating} / 5.0 Rating</span>
                  </div>
                  
                  <div className="flex items-center gap-2">
                    <User className="w-5 h-5 text-blue-500" />
                    <span>{hospital.doctors} Doctors</span>
                  </div>
                  
                  <div className="flex items-center gap-2">
                    <Activity className="w-5 h-5 text-green-500" />
                    <span>Specialties: {hospital.specialties.join(", ")}</span>
                  </div>
                  
                  <div className="flex items-center gap-2">
                    <Package className="w-5 h-5 text-purple-500" />
                    <span>Medicine Status: {hospital.medicines}</span>
                  </div>
                  
                  <button className="w-full mt-4 bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700 transition-colors">
                    View Details
                  </button>
                </div>
              </CardContent>
            </Card>
          ))}
        </div>
      </div>
    </div>
  );
};

export default HospitalPlatform;import React, { useState } from 'react';
import { Search, MapPin, Star, Activity, User, Package } from 'lucide-react';
import {
  Card,
  CardContent,
  CardDescription,
  CardHeader,
  CardTitle,
} from "@/components/ui/card";

const HospitalPlatform = () => {
  const [searchTerm, setSearchTerm] = useState('');
  
  const hospitals = [
    {
      id: 1,
      name: "Kenyatta National Hospital",
      type: "Public",
      location: "Nairobi",
      rating: 4.2,
      doctors: 350,
      specialties: ["Surgery", "Oncology", "Pediatrics"],
      equipment: ["MRI", "CT Scan", "X-Ray"],
      medicines: "Well Stocked",
    },
    {
      id: 2,
      name: "Aga Khan University Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.5,
      doctors: 200,
      specialties: ["Cardiology", "Neurology", "Orthopedics"],
      equipment: ["MRI", "CT Scan", "Ultrasound"],
      medicines: "Fully Stocked",
    },
    {
      id: 3,
      name: "Moi Teaching & Referral Hospital",
      type: "Public",
      location: "Eldoret",
      rating: 4.0,
      doctors: 250,
      specialties: ["General Medicine", "Surgery", "Obstetrics"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Well Stocked",
    },
    {
      id: 4,
      name: "Nairobi Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.6,
      doctors: 180,
      specialties: ["Cardiology", "Oncology", "Pediatrics"],
      equipment: ["MRI", "CT Scan", "PET Scan"],
      medicines: "Fully Stocked",
    },
    {
      id: 5,
      name: "Coast General Hospital",
      type: "Public",
      location: "Mombasa",
      rating: 3.8,
      doctors: 150,
      specialties: ["General Medicine", "Surgery", "Emergency Care"],
      equipment: ["X-Ray", "CT Scan", "Ultrasound"],
      medicines: "Well Stocked",
    },
    {
      id: 6,
      name: "Gertrude's Children's Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.4,
      doctors: 90,
      specialties: ["Pediatrics", "Child Surgery", "Vaccination"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Fully Stocked",
    },
    {
      id: 7,
      name: "Kisumu County Referral Hospital",
      type: "Public",
      location: "Kisumu",
      rating: 3.9,
      doctors: 120,
      specialties: ["General Medicine", "Maternity", "HIV Care"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    },
    {
      id: 8,
      name: "MP Shah Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.3,
      doctors: 150,
      specialties: ["Surgery", "Internal Medicine", "Dermatology"],
      equipment: ["MRI", "CT Scan", "Mammography"],
      medicines: "Fully Stocked",
    },
    {
      id: 9,
      name: "Nakuru Level 5 Hospital",
      type: "Public",
      location: "Nakuru",
      rating: 3.7,
      doctors: 100,
      specialties: ["General Medicine", "Emergency Care", "Obstetrics"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Well Stocked",
    },
    {
      id: 10,
      name: "Karen Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.4,
      doctors: 120,
      specialties: ["Cardiology", "Neurology", "Orthopedics"],
      equipment: ["MRI", "CT Scan", "Cardiac Cath Lab"],
      medicines: "Fully Stocked",
    },
    {
      id: 11,
      name: "Machakos Level 5 Hospital",
      type: "Public",
      location: "Machakos",
      rating: 3.8,
      doctors: 90,
      specialties: ["General Medicine", "Surgery", "Pediatrics"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    },
    {
      id: 12,
      name: "Coptic Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.1,
      doctors: 80,
      specialties: ["General Medicine", "Surgery", "Dental Care"],
      equipment: ["X-Ray", "CT Scan", "Dental Equipment"],
      medicines: "Well Stocked",
    },
    {
      id: 13,
      name: "Nyeri County Referral Hospital",
      type: "Public",
      location: "Nyeri",
      rating: 3.6,
      doctors: 85,
      specialties: ["General Medicine", "Maternity", "Emergency Care"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Moderately Stocked",
    },
    {
      id: 14,
      name: "Avenue Hospital",
      type: "Private",
      location: "Kisumu",
      rating: 4.2,
      doctors: 70,
      specialties: ["Surgery", "Pediatrics", "Obstetrics"],
      equipment: ["MRI", "CT Scan", "Ultrasound"],
      medicines: "Fully Stocked",
    },
    {
      id: 15,
      name: "Kakamega County Referral Hospital",
      type: "Public",
      location: "Kakamega",
      rating: 3.7,
      doctors: 95,
      specialties: ["General Medicine", "Surgery", "HIV Care"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Well Stocked",
    },
    {
      id: 16,
      name: "Mater Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.3,
      doctors: 130,
      specialties: ["Cardiology", "Oncology", "Neurology"],
      equipment: ["MRI", "CT Scan", "Cardiac Cath Lab"],
      medicines: "Fully Stocked",
    },
    {
      id: 17,
      name: "Embu Level 5 Hospital",
      type: "Public",
      location: "Embu",
      rating: 3.8,
      doctors: 80,
      specialties: ["General Medicine", "Surgery", "Pediatrics"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Moderately Stocked",
    },
    {
      id: 18,
      name: "Pandya Memorial Hospital",
      type: "Private",
      location: "Mombasa",
      rating: 4.1,
      doctors: 90,
      specialties: ["Surgery", "Internal Medicine", "Cardiology"],
      equipment: ["MRI", "CT Scan", "Ultrasound"],
      medicines: "Well Stocked",
    },
    {
      id: 19,
      name: "Garissa County Referral Hospital",
      type: "Public",
      location: "Garissa",
      rating: 3.5,
      doctors: 60,
      specialties: ["General Medicine", "Emergency Care", "Maternity"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    },
    {
      id: 20,
      name: "Nairobi Women's Hospital",
      type: "Private",
      location: "Nairobi",
      rating: 4.2,
      doctors: 100,
      specialties: ["Obstetrics", "Gynecology", "Pediatrics"],
      equipment: ["MRI", "Ultrasound", "Mammography"],
      medicines: "Fully Stocked",
    },
    {
      id: 21,
      name: "Kericho County Referral Hospital",
      type: "Public",
      location: "Kericho",
      rating: 3.7,
      doctors: 75,
      specialties: ["General Medicine", "Surgery", "HIV Care"],
      equipment: ["X-Ray", "Ultrasound", "ECG"],
      medicines: "Well Stocked",
    },
    {
      id: 22,
      name: "Outspan Hospital",
      type: "Private",
      location: "Nyeri",
      rating: 4.0,
      doctors: 65,
      specialties: ["Internal Medicine", "Surgery", "Pediatrics"],
      equipment: ["CT Scan", "Ultrasound", "X-Ray"],
      medicines: "Well Stocked",
    },
    {
      id: 23,
      name: "Mama Lucy Kibaki Hospital",
      type: "Public",
      location: "Nairobi",
      rating: 3.8,
      doctors: 85,
      specialties: ["General Medicine", "Maternity", "Emergency Care"],
      equipment: ["X-Ray", "Ultrasound", "Basic Surgery Equipment"],
      medicines: "Moderately Stocked",
    }
  ];

  const filteredHospitals = hospitals.filter(hospital =>
    hospital.name.toLowerCase().includes(searchTerm.toLowerCase()) ||
    hospital.location.toLowerCase().includes(searchTerm.toLowerCase())
  );

  return (
    <div className="min-h-screen bg-gray-50 p-8">
      {/* Header */}
      <div className="max-w-6xl mx-auto">
        <h1 className="text-4xl font-bold text-center mb-2">Kenya Hospital Services Directory</h1>
        <p className="text-gray-600 text-center mb-8">Find and compare healthcare facilities across Kenya</p>
        
        {/* Search Bar */}
        <div className="relative mb-8">
          <input
            type="text"
            placeholder="Search hospitals by name or location..."
            className="w-full p-4 rounded-lg border shadow-sm focus:ring-2 focus:ring-blue-500"
            value={searchTerm}
            onChange={(e) => setSearchTerm(e.target.value)}
          />
          <Search className="absolute right-4 top-4 text-gray-400" />
        </div>

        {/* Hospital Cards */}
        <div className="grid gap-6 md:grid-cols-2 lg:grid-cols-3">
          {filteredHospitals.map(hospital => (
            <Card key={hospital.id} className="hover:shadow-lg transition-shadow">
              <CardHeader>
                <CardTitle className="flex items-center justify-between">
                  <span>{hospital.name}</span>
                  <span className="text-sm px-2 py-1 bg-blue-100 text-blue-800 rounded">
                    {hospital.type}
                  </span>
                </CardTitle>
                <CardDescription className="flex items-center gap-1">
                  <MapPin className="w-4 h-4" />
                  {hospital.location}
                </CardDescription>
              </CardHeader>
              <CardContent>
                <div className="space-y-4">
                  <div className="flex items-center gap-2">
                    <Star className="w-5 h-5 text-yellow-500" />
                    <span>{hospital.rating} / 5.0 Rating</span>
                  </div>
                  
                  <div className="flex items-center gap-2">
                    <User className="w-5 h-5 text-blue-500" />
                    <span>{hospital.doctors} Doctors</span>
                  </div>
                  
                  <div className="flex items-center gap-2">
                    <Activity className="w-5 h-5 text-green-500" />
                    <span>Specialties: {hospital.specialties.join(", ")}</span>
                  </div>
                  
                  <div className="flex items-center gap-2">
                    <Package className="w-5 h-5 text-purple-500" />
                    <span>Medicine Status: {hospital.medicines}</span>
                  </div>
                  
                  <button className="w-full mt-4 bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700 transition-colors">
                    View Details
                  </button>
                </div>
              </CardContent>
            </Card>
          ))}
        </div>
      </div>
    </div>
  );
};

export default HospitalPlatform;
