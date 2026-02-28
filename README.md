### NAMA: Rizky Wahyu Dina Putri
### NIM: 2409116111

# APLIKASI PENDAFTARAN RELAWAN KEGIATAN SOSIAL SAMARINDA
## Deskripsi 
GoVolunteer adalah aplikasi mobile berbasis Flutter yang dirancang sebagai platform promosi dan manajemen kegiatan sosial di Kota Samarinda. Aplikasi ini menjadi jembatan antara organisasi atau komunitas sosial yang ingin menyelenggarakan kegiatan sukarela dengan masyarakat umum (mahasiswa, warga, dan relawan) yang ingin ikut berkontribusi dalam berbagai kegiatan sosial.

Aplikasi ini bertujuan untuk memberikan informasi lengkap mengenai kegiatan yang sedang berlangsung, termasuk lokasi, waktu pelaksanaan, serta manfaat atau benefit yang dapat diperoleh peserta. Selain itu, GoVolunteer memudahkan masyarakat untuk menemukan dan mengikuti kegiatan sosial dengan lebih cepat dan terorganisir.
## Fitur
### Halaman Publik (Masyarakat / Relawan)
#### 1. Daftar Kegiatan (Home)
Menampilkan semua kegiatan sosial dalam bentuk kartu bergambar dengan banner gradient berwarna berbeda per kategori. Dilengkapi filter kategori (Semua, Lingkungan, Kesehatan, Pendidikan, Sosial) sehingga pengguna dapat menyaring kegiatan sesuai minat.
#### 2. Detail Kegiatan
Halaman detail menampilkan informasi lengkap kegiatan: nama kegiatan, nama organisasi penyelenggara, tanggal pelaksanaan, waktu, lokasi, deskripsi kegiatan, dan benefit yang didapat relawan. Terdapat progress bar kapasitas peserta dan indikator sisa slot secara real-time.
#### 3. Form Pendaftaran Relawan
Form pendaftaran dengan 4 input field: Nama Lengkap, Nomor WhatsApp, Email, dan Asal Instansi/Kampus. Terdapat Validasi seperti format email wajib menggunakan regex (harus ada karakter sebelum @, domain valid, ekstensi minimal 2 huruf), format nomor HP wajib diawali 08/+62, agar tidak ada kesalahan saat input data pribadi.
#### 4. Kartu Kegiatan (ActivityCard)
Pada halaman Home terdapat Komponen kartu kegiatan yang sedang berlangsung, terdapat deskripsi singkat mengenai kegiatan, tanggal, jam, progress bar slot dan sisa slot relawan yang dapat mendaftar. Di setiap card juga terdapat tombol detail dan registrasi untuk pengguna.

### Halaman Admin
#### 1. CREATE - Tambah Kegiatan Baru
Form tambah kegiatan dengan 8+ input field: Nama Kegiatan, Nama Organisasi, Kategori, Tanggal , Waktu, Lokasi, Deskripsi, Benefit Relawan, dan Maksimal Peserta. Pada tambah kegiatan baru, format tanggal dibuat seperti kalender yang memudahkan dalam pengisian tanggal dan pemilihan tanggal hanya bisa dipilih mulai hari ini atau hari kedepannya, tidak bisa memilih hari sebelumnya atau tanggal yang udah lalu.
#### 2. READ - Tampilkan Semua Kegiatan
Panel admin menampilkan seluruh kegiatan dalam daftar tile beserta statistik seperti total kegiatan aktif dan total relawan yang sudah terdaftar di semua kegiatan.
#### 3. UPDATE - Edit Kegiatan
Form edit kegiatan yang otomatis terisi dengan data kegiatan yang dipilih. Data dapat diubah dan semua informasi kegiatan diperbarui.
#### 4. DELETE - Hapus Kegiatan
Penghapusan kegiatan disertai dialog konfirmasi untuk mencegah penghapusan tidak sengaja. Saat kegiatan dihapus, seluruh data peserta yang terdaftar juga ikut dihapus secara otomatis.
#### 5. Kelola Peserta
Admin dapat melihat daftar lengkap peserta per kegiatan (nama, email, nomor HP, asal instansi) dan menghapus peserta tertentu. Slot kegiatan akan otomatis bertambah kembali setelah peserta dihapus.

## Widget
### Widget Struktur & Layout
#### 1. Scaffold
Kerangka dasar halaman Flutter yang menyediakan AppBar, body, bottomNavigationBar, dan FloatingActionButton. Digunakan di semua screen untuk membentuk struktur utama halaman (home, detail, form, admin, peserta, register).
#### 2. AppBar
Bilah navigasi di bagian atas halaman yang berisi judul dan tombol aksi.
Digunakan untuk menampilkan identitas halaman serta tombol navigasi (admin, tambah kegiatan, dll).
#### 3. SliverAppBar + CustomScrollView
AppBar yang dapat mengecil saat discroll. Digunakan di halaman detail kegiatan untuk efek banner collapse yang modern dan hemat ruang.
#### 4. Column
Menyusun widget secara vertikal (atas ke bawah).
Digunakan untuk menyusun form, isi kartu, dan konten halaman.
#### 5. Row
Menyusun widget secara horizontal (kiri ke kanan). Digunakan untuk menampilkan ikon dan teks sejajar atau kartu statistik berdampingan.
#### 6. Expanded
Membuat widget mengisi sisa ruang dalam Row/Column. Digunakan untuk mengatur proporsi tombol dan kartu agar responsif.
#### 7. Stack + Positioned
Menumpuk widget seperti layer dan mengatur posisinya.
Digunakan pada banner kartu kegiatan (badge kategori, status penuh, ikon, judul).
#### 8. SingleChildScrollView
Membuat konten bisa discroll jika melebihi layar. Digunakan pada halaman form dengan banyak input.
#### 9. ListView.builder
Membuat daftar scrollable secara efisien. Digunakan untuk menampilkan daftar kegiatan dan peserta.

### Widget Tampilan & Dekorasi
#### 1. Container
Widget serbaguna untuk ukuran, warna, padding, border, dan bayangan.
Digunakan sebagai pembungkus kartu dan kotak informasi.
#### 2. BoxDecoration
Mengatur dekorasi Container (gradient, border radius, shadow).
Digunakan untuk membuat kartu dengan sudut melengkung dan efek bayangan.
#### 3. LinearGradient
Membuat latar belakang gradasi warna. Digunakan pada banner kategori kegiatan.
#### 4. ClipRRect
Memotong widget agar memiliki sudut melengkung. Digunakan pada banner kartu dan progress bar.
#### 5. LinearProgressIndicator
Progress bar horizontal (0.0–1.0). Digunakan untuk menampilkan jumlah slot peserta yang terisi.
#### 6. CircularProgressIndicator
Loading berbentuk lingkaran. Digunakan saat proses submit atau login berlangsung.
#### 7. Icon
Menampilkan ikon Material Design. Digunakan sebagai elemen visual kategori, informasi, dan aksi.

### Widget Teks & Input
#### 1. TextFormField
Input teks dengan validasi Form. Digunakan untuk input nama, email, WA, instansi, dan data kegiatan.
#### 3. TextEditingController
Mengontrol dan membaca nilai input.Digunakan untuk mengambil dan mengisi data form.
#### 4. InputDecoration
Mengatur tampilan TextFormField (hint, border, warna error). Memberikan feedback visual pada kondisi normal, fokus, dan error.
#### 5. DropdownButtonFormField
Dropdown terintegrasi dengan Form. Digunakan untuk memilih kategori kegiatan.
#### 6. Form + GlobalKey<FormState>
Mengelompokkan input dan menjalankan validasi sekaligus. Digunakan saat submit form register, login, dan tambah/edit kegiatan.
### Widget Interaksi & Navigasi
#### 7. ElevatedButton
Tombol utama dengan yang Digunakan untuk aksi penting seperti daftar dan simpan.
#### 8. OutlinedButton
Tombol dengan border tanpa background. Digunakan untuk aksi sekunder seperti tombol “Detail”.
#### 9. TextButton
Tombol sederhana berbasis teks. Digunakan pada dialog konfirmasi.
#### 10. IconButton
Tombol berbentuk ikon. Digunakan di AppBar dan daftar admin (edit, hapus, peserta).
#### 11. FloatingActionButton.extended
Tombol aksi mengambang dengan ikon dan teks. Digunakan untuk menambah kegiatan di halaman admin.
#### 12. GestureDetector
Mendeteksi gesture (tap). Digunakan agar seluruh kartu dapat diklik dan membuka halaman detail.
#### 13. AlertDialog
Dialog popup untuk konfirmasi atau informasi. Digunakan saat hapus data dan notifikasi sukses.
#### 14. SnackBar
Notifikasi singkat di bagian bawah layar. Digunakan untuk pesan sukses dan error.

### Navigasi
#### 1. Navigator.push + MaterialPageRoute
Berpindah ke halaman baru. Digunakan untuk membuka detail, register, form, dan peserta.
#### 2. Navigator.pop
Kembali ke halaman sebelumnya. Digunakan setelah submit berhasil atau menutup dialog.

### State Management (Provider)
#### 1. StatefulWidget + setState()
Mengelola state lokal dalam satu halaman. Digunakan untuk filter kategori dan status loading.
#### 2. ChangeNotifierProvider
Menyediakan state global ke seluruh aplikasi. Digunakan di main.dart untuk mengelola data kegiatan dan peserta.

## Struktur Project
<img width="1085" height="534" alt="image" src="https://github.com/user-attachments/assets/0bed2838-2430-4596-8688-5071671d136f" />

## Dependencies
```dart
dependencies:
  flutter:
    sdk: flutter
  flutter_localizations:
    sdk: flutter
  provider: ^6.1.1        # State management reaktif
  uuid: ^4.2.1            # Generate ID unik untuk setiap kegiatan & peserta
  intl: ^0.20.2           # Format tanggal Bahasa Indonesia
  cupertino_icons: ^1.0.6
```

# CODE
## Package Models
```dart
class Activity {
  final String id;
  String title;
  String organizer;
  String description;
  String location;
  String date;
  String time;
  String benefits;
  int maxParticipants;
  int registeredCount;
  String category;

  Activity({
    required this.id,
    required this.title,
    required this.organizer,
    required this.description,
    required this.location,
    required this.date,
    required this.time,
    required this.benefits,
    required this.maxParticipants,
    this.registeredCount = 0,
    required this.category,
  });

  int get availableSlots => maxParticipants - registeredCount;
  bool get isFull => registeredCount >= maxParticipants;

  Map<String, dynamic> toMap() {
    return {
      'id': id,
      'title': title,
      'organizer': organizer,
      'description': description,
      'location': location,
      'date': date,
      'time': time,
      'benefits': benefits,
      'maxParticipants': maxParticipants,
      'registeredCount': registeredCount,
      'category': category,
    };
  }
}
```
```dart
class Participant {
  final String id;
  final String activityId;
  final String name;
  final String phone;
  final String email;
  final String institution;
  final String registeredAt;

  Participant({
    required this.id,
    required this.activityId,
    required this.name,
    required this.phone,
    required this.email,
    required this.institution,
    required this.registeredAt,
  });
}
```

## Package Providers
```dart
import 'package:flutter/foundation.dart';
import '../models/activity.dart';
import '../models/participant.dart';
import 'package:uuid/uuid.dart';

const _uuid = Uuid();

class AppProvider extends ChangeNotifier {
  final List<Activity> _activities = [];
  final List<Participant> _participants = [];

  List<Activity> get activities => List.unmodifiable(_activities);

  List<Participant> getParticipantsFor(String activityId) =>
      _participants.where((p) => p.activityId == activityId).toList();

  // CREATE
  void addActivity(Activity activity) {
    _activities.add(activity);
    notifyListeners();
  }

  // UPDATE
  void updateActivity(Activity updated) {
    final index = _activities.indexWhere((a) => a.id == updated.id);
    if (index != -1) {
      _activities[index] = updated;
      notifyListeners();
    }
  }

  // DELETE
  void deleteActivity(String id) {
    _activities.removeWhere((a) => a.id == id);
    _participants.removeWhere((p) => p.activityId == id);
    notifyListeners();
  }

  // REGISTER
  bool registerParticipant({
    required String activityId,
    required String name,
    required String phone,
    required String email,
    required String institution,
  }) {
    final activityIndex = _activities.indexWhere((a) => a.id == activityId);
    if (activityIndex == -1) return false;

    final activity = _activities[activityIndex];
    if (activity.isFull) return false;

    // Simpan peserta
    final participant = Participant(
      id: _uuid.v4(),
      activityId: activityId,
      name: name,
      phone: phone,
      email: email,
      institution: institution,
      registeredAt: DateTime.now().toIso8601String(),
    );
    _participants.add(participant);

    // Rebuild activity dengan registeredCount baru
    _activities[activityIndex] = Activity(
      id: activity.id,
      title: activity.title,
      organizer: activity.organizer,
      description: activity.description,
      location: activity.location,
      date: activity.date,
      time: activity.time,
      benefits: activity.benefits,
      maxParticipants: activity.maxParticipants,
      registeredCount: activity.registeredCount + 1,
      category: activity.category,
    );

    notifyListeners();
    return true;
  }

  // DELETE Participant
  void removeParticipant(String participantId, String activityId) {
    _participants.removeWhere((p) => p.id == participantId);

    final activityIndex = _activities.indexWhere((a) => a.id == activityId);
    if (activityIndex != -1 && _activities[activityIndex].registeredCount > 0) {
      final activity = _activities[activityIndex];
      _activities[activityIndex] = Activity(
        id: activity.id,
        title: activity.title,
        organizer: activity.organizer,
        description: activity.description,
        location: activity.location,
        date: activity.date,
        time: activity.time,
        benefits: activity.benefits,
        maxParticipants: activity.maxParticipants,
        registeredCount: activity.registeredCount - 1,
        category: activity.category,
      );
    }

    notifyListeners();
  }

  Activity createNewActivity({
    required String title,
    required String organizer,
    required String description,
    required String location,
    required String date,
    required String time,
    required String benefits,
    required int maxParticipants,
    required String category,
  }) {
    return Activity(
      id: _uuid.v4(),
      title: title,
      organizer: organizer,
      description: description,
      location: location,
      date: date,
      time: time,
      benefits: benefits,
      maxParticipants: maxParticipants,
      category: category,
    );
  }
}
```
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import '../models/activity.dart';
import '../providers/app_provider.dart';
import 'register_screen.dart';

class ActivityDetailScreen extends StatelessWidget {
  final Activity activity;

  const ActivityDetailScreen({super.key, required this.activity});

  @override
  Widget build(BuildContext context) {
    final provider = context.watch<AppProvider>();
    // Refresh activity data
    final current = provider.activities.firstWhere(
      (a) => a.id == activity.id,
      orElse: () => activity,
    );
    final slotPercent = current.maxParticipants > 0
        ? current.registeredCount / current.maxParticipants
        : 0.0;

    return Scaffold(
      backgroundColor: const Color(0xFFF0F4FF),
      body: CustomScrollView(
        slivers: [
          SliverAppBar(
            expandedHeight: 180,
            pinned: true,
            backgroundColor: const Color(0xFF1565C0),
            foregroundColor: Colors.white,
            flexibleSpace: FlexibleSpaceBar(
              background: Container(
                decoration: const BoxDecoration(
                  gradient: LinearGradient(
                    begin: Alignment.topLeft,
                    end: Alignment.bottomRight,
                    colors: [Color(0xFF0D47A1), Color(0xFF1E88E5)],
                  ),
                ),
                child: const Center(
                  child: Icon(Icons.volunteer_activism, size: 72, color: Colors.white24),
                ),
              ),
            ),
          ),

          SliverToBoxAdapter(
            child: Padding(
              padding: const EdgeInsets.all(16),
              child: Column(
                crossAxisAlignment: CrossAxisAlignment.start,
                children: [
                  // Title card
                  Container(
                    width: double.infinity,
                    padding: const EdgeInsets.all(16),
                    decoration: BoxDecoration(
                      color: Colors.white,
                      borderRadius: BorderRadius.circular(16),
                      boxShadow: [BoxShadow(color: Colors.black.withValues(alpha: 0.05), blurRadius: 8)],
                    ),
                    child: Column(
                      crossAxisAlignment: CrossAxisAlignment.start,
                      children: [
                        Container(
                          padding: const EdgeInsets.symmetric(horizontal: 10, vertical: 4),
                          decoration: BoxDecoration(
                            color: const Color(0xFF1565C0).withValues(alpha: 0.1),
                            borderRadius: BorderRadius.circular(20),
                          ),
                          child: Text(
                            current.category,
                            style: const TextStyle(color: Color(0xFF1565C0), fontSize: 12, fontWeight: FontWeight.bold),
                          ),
                        ),
                        const SizedBox(height: 10),
                        Text(
                          current.title,
                          style: const TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
                        ),
                        const SizedBox(height: 4),
                        Text(
                          'oleh ${current.organizer}',
                          style: const TextStyle(color: Colors.grey, fontSize: 13),
                        ),
                      ],
                    ),
                  ),

                  const SizedBox(height: 12),

                  // Info Grid
                  Row(
                    children: [
                      Expanded(child: _infoTile(Icons.calendar_today, 'Tanggal', current.date)),
                      const SizedBox(width: 12),
                      Expanded(child: _infoTile(Icons.access_time, 'Waktu', current.time)),
                    ],
                  ),
                  const SizedBox(height: 12),
                  _infoTile(Icons.location_on, 'Lokasi', current.location),
                  const SizedBox(height: 12),

                  // Slot
                  Container(
                    width: double.infinity,
                    padding: const EdgeInsets.all(16),
                    decoration: BoxDecoration(
                      color: Colors.white,
                      borderRadius: BorderRadius.circular(16),
                      boxShadow: [BoxShadow(color: Colors.black.withValues(alpha: 0.05), blurRadius: 8)],
                    ),
                    child: Column(
                      crossAxisAlignment: CrossAxisAlignment.start,
                      children: [
                        Row(
                          mainAxisAlignment: MainAxisAlignment.spaceBetween,
                          children: [
                            const Text('Kapasitas Relawan', style: TextStyle(fontWeight: FontWeight.bold)),
                            Text(
                              '${current.registeredCount}/${current.maxParticipants} terdaftar',
                              style: TextStyle(
                                color: slotPercent > 0.8 ? Colors.red : const Color(0xFF1565C0),
                                fontWeight: FontWeight.bold,
                                fontSize: 13,
                              ),
                            ),
                          ],
                        ),
                        const SizedBox(height: 8),
                        ClipRRect(
                          borderRadius: BorderRadius.circular(4),
                          child: LinearProgressIndicator(
                            value: slotPercent.toDouble(),
                            backgroundColor: Colors.grey.shade200,
                            valueColor: AlwaysStoppedAnimation(
                              slotPercent > 0.8 ? Colors.red : const Color(0xFF1E88E5),
                            ),
                            minHeight: 8,
                          ),
                        ),
                        const SizedBox(height: 6),
                        Text(
                          current.isFull
                              ? 'Slot penuh! Pendaftaran ditutup.'
                              : '${current.availableSlots} slot tersisa',
                          style: TextStyle(
                            fontSize: 12,
                            color: current.isFull ? Colors.red : Colors.blue.shade700,
                          ),
                        ),
                      ],
                    ),
                  ),

                  const SizedBox(height: 12),

                  // Description
                  _sectionCard('Deskripsi Kegiatan', current.description),
                  const SizedBox(height: 12),
                  _sectionCard('Benefit Relawan', current.benefits),

                  const SizedBox(height: 80),
                ],
              ),
            ),
          ),
        ],
      ),
      bottomNavigationBar: current.isFull
          ? Container(
              padding: const EdgeInsets.all(16),
              child: ElevatedButton(
                onPressed: null,
                style: ElevatedButton.styleFrom(
                  minimumSize: const Size(double.infinity, 52),
                  shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(12)),
                ),
                child: const Text('Slot Penuh'),
              ),
            )
          : Container(
              padding: const EdgeInsets.all(16),
              child: ElevatedButton(
                onPressed: () => Navigator.push(
                  context,
                  MaterialPageRoute(
                    builder: (_) => RegisterScreen(activity: current),
                  ),
                ),
                style: ElevatedButton.styleFrom(
                  backgroundColor: const Color(0xFF1565C0),
                  foregroundColor: Colors.white,
                  minimumSize: const Size(double.infinity, 52),
                  shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(12)),
                ),
                child: const Text(
                  'Daftar Sekarang',
                  style: TextStyle(fontSize: 16, fontWeight: FontWeight.bold),
                ),
              ),
            ),
    );
  }

  Widget _infoTile(IconData icon, String label, String value) {
    return Container(
      padding: const EdgeInsets.all(12),
      decoration: BoxDecoration(
        color: Colors.white,
        borderRadius: BorderRadius.circular(12),
        boxShadow: [BoxShadow(color: Colors.black.withValues(alpha: 0.05), blurRadius: 8)],
      ),
      child: Row(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Icon(icon, color: const Color(0xFF1565C0), size: 18),
          const SizedBox(width: 8),
          Expanded(
            child: Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Text(label, style: const TextStyle(color: Colors.grey, fontSize: 11)),
                const SizedBox(height: 2),
                Text(value, style: const TextStyle(fontWeight: FontWeight.w600, fontSize: 13)),
              ],
            ),
          ),
        ],
      ),
    );
  }

  Widget _sectionCard(String title, String content) {
    return Container(
      width: double.infinity,
      padding: const EdgeInsets.all(16),
      decoration: BoxDecoration(
        color: Colors.white,
        borderRadius: BorderRadius.circular(16),
        boxShadow: [BoxShadow(color: Colors.black.withValues(alpha: 0.05), blurRadius: 8)],
      ),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          Text(title, style: const TextStyle(fontWeight: FontWeight.bold, fontSize: 15)),
          const SizedBox(height: 8),
          Text(content, style: const TextStyle(height: 1.5, color: Color(0xFF444444))),
        ],
      ),
    );
  }
}
```
## Package Screens
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import 'package:intl/intl.dart';
import '../models/activity.dart';
import '../providers/app_provider.dart';

class ActivityFormScreen extends StatefulWidget {
  final Activity? activity;

  const ActivityFormScreen({super.key, this.activity});

  @override
  State<ActivityFormScreen> createState() => _ActivityFormScreenState();
}

class _ActivityFormScreenState extends State<ActivityFormScreen> {
  final _formKey = GlobalKey<FormState>();
  late final TextEditingController _titleController;
  late final TextEditingController _organizerController;
  late final TextEditingController _descController;
  late final TextEditingController _locationController;
  late final TextEditingController _timeController;
  late final TextEditingController _benefitsController;
  late final TextEditingController _maxController;

  String _selectedCategory = 'Lingkungan';
  DateTime? _selectedDate;

  final _categories = ['Lingkungan', 'Kesehatan', 'Pendidikan', 'Sosial'];

  bool get isEdit => widget.activity != null;

  @override
  void initState() {
    super.initState();
    final a = widget.activity;
    _titleController = TextEditingController(text: a?.title ?? '');
    _organizerController = TextEditingController(text: a?.organizer ?? '');
    _descController = TextEditingController(text: a?.description ?? '');
    _locationController = TextEditingController(text: a?.location ?? '');
    _timeController = TextEditingController(text: a?.time ?? '');
    _benefitsController = TextEditingController(text: a?.benefits ?? '');
    _maxController = TextEditingController(text: a?.maxParticipants.toString() ?? '50');
    if (a != null) {
      _selectedCategory = a.category;
      try {
        _selectedDate = DateFormat('d MMMM yyyy', 'id_ID').parse(a.date);
      } catch (_) {
        _selectedDate = null;
      }
    }
  }

  @override
  void dispose() {
    for (final c in [
      _titleController, _organizerController, _descController,
      _locationController, _timeController, _benefitsController, _maxController,
    ]) {
      c.dispose();
    }
    super.dispose();
  }

  // Format tanggal ke bahasa Indonesia
  String _formatDate(DateTime date) {
    final months = [
      '', 'Januari', 'Februari', 'Maret', 'April', 'Mei', 'Juni',
      'Juli', 'Agustus', 'September', 'Oktober', 'November', 'Desember',
    ];
    return '${date.day} ${months[date.month]} ${date.year}';
  }

  Future<void> _pickDate() async {
    final today = DateTime.now();
    final firstDate = DateTime(today.year, today.month, today.day);

    final picked = await showDatePicker(
      context: context,
      initialDate: _selectedDate != null && _selectedDate!.isAfter(firstDate)
          ? _selectedDate!
          : firstDate,
      firstDate: firstDate,           
      lastDate: DateTime(today.year + 3), // max 3 tahun ke depan
      locale: const Locale('id', 'ID'),
      builder: (context, child) {
        return Theme(
          data: Theme.of(context).copyWith(
            colorScheme: const ColorScheme.light(
              primary: Color(0xFF1565C0),
              onPrimary: Colors.white,
              onSurface: Color(0xFF1A1A1A),
              surface: Colors.white,
            ),
          ),
          child: child!,
        );
      },
    );

    if (picked != null) {
      setState(() => _selectedDate = picked);
    }
  }

  void _save() {
    if (!_formKey.currentState!.validate()) return;
    if (_selectedDate == null) {
      ScaffoldMessenger.of(context).showSnackBar(
        const SnackBar(
          content: Text('Tanggal kegiatan wajib dipilih!'),
          backgroundColor: Colors.red,
        ),
      );
      return;
    }

    final provider = context.read<AppProvider>();
    final dateString = _formatDate(_selectedDate!);

    if (isEdit) {
      final updated = Activity(
        id: widget.activity!.id,
        title: _titleController.text.trim(),
        organizer: _organizerController.text.trim(),
        description: _descController.text.trim(),
        location: _locationController.text.trim(),
        date: dateString,
        time: _timeController.text.trim(),
        benefits: _benefitsController.text.trim(),
        maxParticipants: int.tryParse(_maxController.text) ?? 50,
        registeredCount: widget.activity!.registeredCount,
        category: _selectedCategory,
      );
      provider.updateActivity(updated);
      ScaffoldMessenger.of(context).showSnackBar(
        const SnackBar(content: Text('Kegiatan berhasil diperbarui!'), backgroundColor: Color(0xFF1565C0)),
      );
    } else {
      final activity = provider.createNewActivity(
        title: _titleController.text.trim(),
        organizer: _organizerController.text.trim(),
        description: _descController.text.trim(),
        location: _locationController.text.trim(),
        date: dateString,
        time: _timeController.text.trim(),
        benefits: _benefitsController.text.trim(),
        maxParticipants: int.tryParse(_maxController.text) ?? 50,
        category: _selectedCategory,
      );
      provider.addActivity(activity);
      ScaffoldMessenger.of(context).showSnackBar(
        const SnackBar(content: Text('Kegiatan berhasil ditambahkan!'), backgroundColor: Color(0xFF1565C0)),
      );
    }
    Navigator.pop(context);
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: const Color(0xFFF0F4FF),
      appBar: AppBar(
        backgroundColor: const Color(0xFF1565C0),
        foregroundColor: Colors.white,
        title: Text(isEdit ? 'Edit Kegiatan' : 'Tambah Kegiatan'),
        elevation: 0,
      ),
      body: SingleChildScrollView(
        padding: const EdgeInsets.all(16),
        child: Form(
          key: _formKey,
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              _field(_titleController, 'Nama Kegiatan', 'Contoh: Bersih-Bersih Pantai', Icons.event),
              const SizedBox(height: 12),
              _field(_organizerController, 'Nama Organisasi', 'Contoh: Komunitas Hijau Samarinda', Icons.groups),
              const SizedBox(height: 12),

              // Category Dropdown
              const Text('Kategori', style: TextStyle(fontWeight: FontWeight.w600, fontSize: 13)),
              const SizedBox(height: 6),
              DropdownButtonFormField<String>(
                initialValue: _selectedCategory,
                decoration: _inputDecoration(Icons.category, 'Pilih kategori'),
                items: _categories
                    .map((c) => DropdownMenuItem(value: c, child: Text(c)))
                    .toList(),
                onChanged: (v) => setState(() => _selectedCategory = v!),
              ),

              const SizedBox(height: 12),

              // Kalender Tanggal
              const Text('Tanggal Kegiatan', style: TextStyle(fontWeight: FontWeight.w600, fontSize: 13)),
              const SizedBox(height: 6),
              GestureDetector(
                onTap: _pickDate,
                child: Container(
                  width: double.infinity,
                  padding: const EdgeInsets.symmetric(horizontal: 12, vertical: 14),
                  decoration: BoxDecoration(
                    color: Colors.white,
                    borderRadius: BorderRadius.circular(12),
                    border: Border.all(
                      color: _selectedDate == null
                          ? Colors.grey.shade300
                          : const Color(0xFF1565C0),
                      width: _selectedDate == null ? 1 : 1.5,
                    ),
                  ),
                  child: Row(
                    children: [
                      Icon(
                        Icons.calendar_month,
                        color: _selectedDate == null
                            ? const Color(0xFF1565C0)
                            : const Color(0xFF1565C0),
                        size: 20,
                      ),
                      const SizedBox(width: 12),
                      Expanded(
                        child: Text(
                          _selectedDate == null
                              ? 'Pilih tanggal kegiatan...'
                              : _formatDate(_selectedDate!),
                          style: TextStyle(
                            fontSize: 14,
                            color: _selectedDate == null
                                ? Colors.grey.shade400
                                : const Color(0xFF1A1A1A),
                            fontWeight: _selectedDate == null
                                ? FontWeight.normal
                                : FontWeight.w600,
                          ),
                        ),
                      ),
                      Icon(
                        Icons.arrow_drop_down,
                        color: Colors.grey.shade400,
                      ),
                    ],
                  ),
                ),
              ),
              // Hint text under date picker
              Padding(
                padding: const EdgeInsets.only(top: 4, left: 4),
                child: Text(
                  'Hanya dapat memilih tanggal hari ini atau yang akan datang',
                  style: TextStyle(fontSize: 11, color: Colors.grey.shade500),
                ),
              ),

              const SizedBox(height: 12),
              _field(_timeController, 'Waktu Kegiatan', 'Contoh: 07.00 - 12.00 WITA', Icons.access_time),
              const SizedBox(height: 12),
              _field(_locationController, 'Lokasi Kegiatan', 'Contoh: Sungai Mahakam, Samarinda', Icons.location_on),
              const SizedBox(height: 12),
              _field(
                _descController,
                'Deskripsi Kegiatan',
                'Jelaskan detail kegiatan ini...',
                Icons.description,
                maxLines: 4,
              ),
              const SizedBox(height: 12),
              _field(
                _benefitsController,
                'Benefit Relawan',
                'Contoh: Sertifikat, Kaos, Snack',
                Icons.card_giftcard,
                maxLines: 2,
              ),
              const SizedBox(height: 12),
              _field(
                _maxController,
                'Maksimal Peserta',
                'Contoh: 100',
                Icons.people,
                keyboardType: TextInputType.number,
                validator: (v) {
                  if (v == null || v.isEmpty) return 'Wajib diisi';
                  if (int.tryParse(v) == null || int.parse(v) <= 0) return 'Masukkan angka valid';
                  return null;
                },
              ),
              const SizedBox(height: 24),

              SizedBox(
                width: double.infinity,
                height: 52,
                child: ElevatedButton(
                  onPressed: _save,
                  style: ElevatedButton.styleFrom(
                    backgroundColor: const Color(0xFF1565C0),
                    foregroundColor: Colors.white,
                    shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(12)),
                  ),
                  child: Text(
                    isEdit ? 'Simpan Perubahan' : 'Tambah Kegiatan',
                    style: const TextStyle(fontSize: 16, fontWeight: FontWeight.bold),
                  ),
                ),
              ),
              const SizedBox(height: 20),
            ],
          ),
        ),
      ),
    );
  }

  InputDecoration _inputDecoration(IconData icon, String hint) {
    return InputDecoration(
      hintText: hint,
      prefixIcon: Icon(icon, color: const Color(0xFF1565C0), size: 20),
      filled: true,
      fillColor: Colors.white,
      border: OutlineInputBorder(
          borderRadius: BorderRadius.circular(12),
          borderSide: BorderSide(color: Colors.grey.shade300)),
      enabledBorder: OutlineInputBorder(
          borderRadius: BorderRadius.circular(12),
          borderSide: BorderSide(color: Colors.grey.shade300)),
      focusedBorder: OutlineInputBorder(
          borderRadius: BorderRadius.circular(12),
          borderSide: const BorderSide(color: Color(0xFF1565C0), width: 2)),
      errorBorder: OutlineInputBorder(
          borderRadius: BorderRadius.circular(12),
          borderSide: const BorderSide(color: Colors.red)),
      contentPadding: const EdgeInsets.symmetric(horizontal: 12, vertical: 14),
    );
  }

  Widget _field(
    TextEditingController controller,
    String label,
    String hint,
    IconData icon, {
    TextInputType? keyboardType,
    int? maxLines,
    String? Function(String?)? validator,
  }) {
    return Column(
      crossAxisAlignment: CrossAxisAlignment.start,
      children: [
        Text(label, style: const TextStyle(fontWeight: FontWeight.w600, fontSize: 13)),
        const SizedBox(height: 6),
        TextFormField(
          controller: controller,
          keyboardType: keyboardType,
          maxLines: maxLines ?? 1,
          validator: validator ?? (v) => v == null || v.isEmpty ? '$label wajib diisi' : null,
          decoration: _inputDecoration(icon, hint),
        ),
      ],
    );
  }
}
```
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import '../providers/app_provider.dart';
import '../models/activity.dart';
import 'activity_form_screen.dart';
import 'participants_screen.dart';

class AdminScreen extends StatelessWidget {
  const AdminScreen({super.key});

  @override
  Widget build(BuildContext context) {
    final provider = context.watch<AppProvider>();
    final activities = provider.activities;

    return Scaffold(
      backgroundColor: const Color(0xFFF0F4FF),
      appBar: AppBar(
        backgroundColor: const Color(0xFF0D47A1),
        foregroundColor: Colors.white,
        title: const Text('Admin Panel'),
        elevation: 0,
        actions: [
          IconButton(
            icon: const Icon(Icons.add_circle_outline),
            tooltip: 'Tambah Kegiatan',
            onPressed: () => Navigator.push(
              context,
              MaterialPageRoute(builder: (_) => const ActivityFormScreen()),
            ),
          ),
        ],
      ),
      body: Column(
        children: [
          // Stats
          Container(
            color: const Color(0xFF0D47A1),
            padding: const EdgeInsets.fromLTRB(16, 0, 16, 20),
            child: Row(
              children: [
                _statCard('Kegiatan', activities.length.toString(), Icons.event),
                const SizedBox(width: 12),
                _statCard(
                  'Total Relawan',
                  activities.fold(0, (s, a) => s + a.registeredCount).toString(),
                  Icons.people,
                ),
              ],
            ),
          ),

          const Padding(
            padding: EdgeInsets.all(16),
            child: Row(
              children: [
                Text('Daftar Kegiatan', style: TextStyle(fontWeight: FontWeight.bold, fontSize: 16)),
              ],
            ),
          ),

          Expanded(
            child: activities.isEmpty
                ? const Center(child: Text('Belum ada kegiatan'))
                : ListView.builder(
                    padding: const EdgeInsets.fromLTRB(16, 0, 16, 80),
                    itemCount: activities.length,
                    itemBuilder: (context, i) => _AdminActivityTile(activity: activities[i]),
                  ),
          ),
        ],
      ),
      floatingActionButton: FloatingActionButton.extended(
        onPressed: () => Navigator.push(
          context,
          MaterialPageRoute(builder: (_) => const ActivityFormScreen()),
        ),
        backgroundColor: const Color(0xFF1565C0),
        foregroundColor: Colors.white,
        icon: const Icon(Icons.add),
        label: const Text('Tambah Kegiatan'),
      ),
    );
  }

  Widget _statCard(String label, String value, IconData icon) {
    return Expanded(
      child: Container(
        padding: const EdgeInsets.all(14),
        decoration: BoxDecoration(
          color: Colors.white.withValues(alpha: 0.15),
          borderRadius: BorderRadius.circular(12),
        ),
        child: Row(
          children: [
            Icon(icon, color: Colors.white70, size: 24),
            const SizedBox(width: 10),
            Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Text(value, style: const TextStyle(color: Colors.white, fontWeight: FontWeight.bold, fontSize: 20)),
                Text(label, style: const TextStyle(color: Colors.white70, fontSize: 12)),
              ],
            ),
          ],
        ),
      ),
    );
  }
}

class _AdminActivityTile extends StatelessWidget {
  final Activity activity;
  const _AdminActivityTile({required this.activity});

  @override
  Widget build(BuildContext context) {
    return Container(
      margin: const EdgeInsets.only(bottom: 10),
      decoration: BoxDecoration(
        color: Colors.white,
        borderRadius: BorderRadius.circular(14),
        boxShadow: [BoxShadow(color: Colors.black.withValues(alpha: 0.05), blurRadius: 6)],
      ),
      child: ListTile(
        contentPadding: const EdgeInsets.fromLTRB(16, 10, 8, 10),
        title: Text(activity.title, style: const TextStyle(fontWeight: FontWeight.bold, fontSize: 14)),
        subtitle: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          children: [
            const SizedBox(height: 4),
            Text(activity.organizer, style: TextStyle(fontSize: 12, color: Colors.grey.shade600)),
            const SizedBox(height: 4),
            Row(
              children: [
                Icon(Icons.people, size: 13, color: Colors.grey.shade500),
                const SizedBox(width: 4),
                Text(
                  '${activity.registeredCount}/${activity.maxParticipants} relawan',
                  style: TextStyle(fontSize: 12, color: Colors.grey.shade600),
                ),
                const SizedBox(width: 8),
                Container(
                  padding: const EdgeInsets.symmetric(horizontal: 6, vertical: 2),
                  decoration: BoxDecoration(
                    color: const Color(0xFF1565C0).withValues(alpha: 0.1),
                    borderRadius: BorderRadius.circular(10),
                  ),
                  child: Text(
                    activity.category,
                    style: const TextStyle(fontSize: 10, color: Color(0xFF1565C0), fontWeight: FontWeight.bold),
                  ),
                ),
              ],
            ),
          ],
        ),
        trailing: Row(
          mainAxisSize: MainAxisSize.min,
          children: [
            IconButton(
              icon: const Icon(Icons.group, color: Colors.blue, size: 20),
              tooltip: 'Lihat Peserta',
              onPressed: () => Navigator.push(
                context,
                MaterialPageRoute(
                  builder: (_) => ParticipantsScreen(activity: activity),
                ),
              ),
            ),
            IconButton(
              icon: const Icon(Icons.edit, color: Color(0xFF1565C0), size: 20),
              tooltip: 'Edit',
              onPressed: () => Navigator.push(
                context,
                MaterialPageRoute(
                  builder: (_) => ActivityFormScreen(activity: activity),
                ),
              ),
            ),
            IconButton(
              icon: const Icon(Icons.delete, color: Colors.red, size: 20),
              tooltip: 'Hapus',
              onPressed: () => _confirmDelete(context),
            ),
          ],
        ),
      ),
    );
  }

  void _confirmDelete(BuildContext context) {
    showDialog(
      context: context,
      builder: (_) => AlertDialog(
        shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(16)),
        title: const Text('Hapus Kegiatan?'),
        content: Text('Kegiatan "${activity.title}" akan dihapus beserta semua data peserta.'),
        actions: [
          TextButton(onPressed: () => Navigator.pop(context), child: const Text('Batal')),
          ElevatedButton(
            style: ElevatedButton.styleFrom(backgroundColor: Colors.red, foregroundColor: Colors.white),
            onPressed: () {
              context.read<AppProvider>().deleteActivity(activity.id);
              Navigator.pop(context);
              ScaffoldMessenger.of(context).showSnackBar(
                const SnackBar(content: Text('Kegiatan berhasil dihapus'), backgroundColor: Colors.red),
              );
            },
            child: const Text('Hapus'),
          ),
        ],
      ),
    );
  }
}
```
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import '../providers/app_provider.dart';
import '../widgets/activity_card.dart';
import 'activity_detail_screen.dart';
import 'register_screen.dart';
import 'admin_screen.dart';

class HomeScreen extends StatefulWidget {
  const HomeScreen({super.key});

  @override
  State<HomeScreen> createState() => _HomeScreenState();
}

class _HomeScreenState extends State<HomeScreen> {
  String _selectedCategory = 'Semua';
  final List<String> _categories = [
    'Semua',
    'Lingkungan',
    'Kesehatan',
    'Pendidikan',
    'Sosial',
  ];

  @override
  Widget build(BuildContext context) {
    final provider = context.watch<AppProvider>();
    final activities = provider.activities.where((a) {
      if (_selectedCategory == 'Semua') return true;
      return a.category == _selectedCategory;
    }).toList();

    return Scaffold(
      backgroundColor: const Color(0xFFF0F4FF),
      appBar: AppBar(
        backgroundColor: const Color(0xFF1565C0),
        foregroundColor: Colors.white,
        elevation: 0,
        automaticallyImplyLeading: false,
        title: const Row(
          children: [
            Icon(Icons.volunteer_activism, color: Colors.white),
            SizedBox(width: 8),
            Text(
              'GoVolunteer',
              style: TextStyle(fontWeight: FontWeight.bold, fontSize: 20),
            ),
          ],
        ),
        actions: [
          IconButton(
            icon: const Icon(Icons.admin_panel_settings),
            tooltip: 'Admin Panel',
            onPressed: () => Navigator.push(
              context,
              MaterialPageRoute(builder: (_) => const AdminScreen()),
            ),
          ),
        ],
      ),
      body: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          // Header Banner
          Container(
            width: double.infinity,
            decoration: const BoxDecoration(
              color: Color(0xFF1565C0),
              borderRadius: BorderRadius.only(
                bottomLeft: Radius.circular(24),
                bottomRight: Radius.circular(24),
              ),
            ),
            padding: const EdgeInsets.fromLTRB(20, 0, 20, 24),
            child: const Column(
              crossAxisAlignment: CrossAxisAlignment.start,
              children: [
                Text(
                  'Halo, Relawan!',
                  style: TextStyle(color: Colors.white70, fontSize: 14),
                ),
                SizedBox(height: 4),
                Text(
                  'Temukan kegiatan sosial\ndi Samarinda',
                  style: TextStyle(
                    color: Colors.white,
                    fontSize: 22,
                    fontWeight: FontWeight.bold,
                    height: 1.3,
                  ),
                ),
              ],
            ),
          ),

          const SizedBox(height: 14),

          // Category Filter chips
          SizedBox(
            height: 36,
            child: ListView.builder(
              scrollDirection: Axis.horizontal,
              padding: const EdgeInsets.symmetric(horizontal: 16),
              itemCount: _categories.length,
              itemBuilder: (context, i) {
                final cat = _categories[i];
                final isSelected = cat == _selectedCategory;
                return GestureDetector(
                  onTap: () => setState(() => _selectedCategory = cat),
                  child: Container(
                    margin: const EdgeInsets.only(right: 8),
                    padding: const EdgeInsets.symmetric(
                        horizontal: 16, vertical: 6),
                    decoration: BoxDecoration(
                      color: isSelected
                          ? const Color(0xFF1565C0)
                          : Colors.white,
                      borderRadius: BorderRadius.circular(20),
                      border: Border.all(
                        color: isSelected
                            ? const Color(0xFF1565C0)
                            : Colors.grey.shade300,
                      ),
                      boxShadow: isSelected
                          ? [
                              BoxShadow(
                                  color: const Color(0xFF1565C0)
                                      .withValues(alpha: 0.3),
                                  blurRadius: 6)
                            ]
                          : null,
                    ),
                    child: Text(
                      cat,
                      style: TextStyle(
                        color: isSelected
                            ? Colors.white
                            : Colors.grey.shade700,
                        fontWeight: isSelected
                            ? FontWeight.bold
                            : FontWeight.normal,
                        fontSize: 13,
                      ),
                    ),
                  ),
                );
              },
            ),
          ),

          const SizedBox(height: 10),

          Padding(
            padding: const EdgeInsets.symmetric(horizontal: 16),
            child: Text(
              '${activities.length} Kegiatan Tersedia',
              style:
                  TextStyle(color: Colors.grey.shade600, fontSize: 13),
            ),
          ),

          const SizedBox(height: 6),

          // Activity Cards
          Expanded(
            child: activities.isEmpty
                ? const Center(
                    child: Column(
                      mainAxisAlignment: MainAxisAlignment.center,
                      children: [
                        Icon(Icons.event_busy,
                            size: 64, color: Colors.grey),
                        SizedBox(height: 12),
                        Text(
                          'Belum ada kegiatan',
                          style: TextStyle(
                              color: Colors.grey, fontSize: 15),
                        ),
                      ],
                    ),
                  )
                : ListView.builder(
                    padding:
                        const EdgeInsets.fromLTRB(16, 0, 16, 100),
                    itemCount: activities.length,
                    itemBuilder: (context, i) {
                      final act = activities[i];
                      return ActivityCard(
                        activity: act,
                        onTap: () => Navigator.push(
                          context,
                          MaterialPageRoute(
                            builder: (_) =>
                                ActivityDetailScreen(activity: act),
                          ),
                        ),
                        onRegister: () => Navigator.push(
                          context,
                          MaterialPageRoute(
                            builder: (_) =>
                                RegisterScreen(activity: act),
                          ),
                        ),
                      );
                    },
                  ),
          ),
        ],
      ),
    );
  }
}
```
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import '../models/activity.dart';
import '../providers/app_provider.dart';

class ParticipantsScreen extends StatelessWidget {
  final Activity activity;
  const ParticipantsScreen({super.key, required this.activity});

  @override
  Widget build(BuildContext context) {
    final provider = context.watch<AppProvider>();
    final participants = provider.getParticipantsFor(activity.id);

    return Scaffold(
      backgroundColor: const Color(0xFFF0F4FF),
      appBar: AppBar(
        backgroundColor: const Color(0xFF0D47A1),
        foregroundColor: Colors.white,
        title: Text('Peserta: ${activity.title}', maxLines: 1, overflow: TextOverflow.ellipsis),
        elevation: 0,
      ),
      body: Column(
        children: [
          Container(
            color: const Color(0xFF0D47A1),
            width: double.infinity,
            padding: const EdgeInsets.fromLTRB(16, 0, 16, 16),
            child: Text(
              '${participants.length} dari ${activity.maxParticipants} slot terisi',
              style: const TextStyle(color: Colors.white70, fontSize: 13),
            ),
          ),

          participants.isEmpty
              ? const Expanded(
                  child: Center(
                    child: Text(
                      'Belum ada peserta terdaftar',
                      style: TextStyle(color: Colors.grey),
                    ),
                  ),
                )
              : Expanded(
                  child: ListView.builder(
                    padding: const EdgeInsets.all(16),
                    itemCount: participants.length,
                    itemBuilder: (context, i) {
                      final p = participants[i];
                      return Container(
                        margin: const EdgeInsets.only(bottom: 10),
                        padding: const EdgeInsets.all(14),
                        decoration: BoxDecoration(
                          color: Colors.white,
                          borderRadius: BorderRadius.circular(12),
                          boxShadow: [
                            BoxShadow(color: Colors.black.withValues(alpha: 0.05), blurRadius: 6)
                          ],
                        ),
                        child: Row(
                          crossAxisAlignment: CrossAxisAlignment.start,
                          children: [
                            Expanded(
                              child: Column(
                                crossAxisAlignment: CrossAxisAlignment.start,
                                children: [
                                  Text(
                                    p.name,
                                    style: const TextStyle(
                                        fontWeight: FontWeight.bold, fontSize: 14),
                                  ),
                                  const SizedBox(height: 4),
                                  Text(p.email,
                                      style: TextStyle(
                                          fontSize: 12, color: Colors.grey.shade600)),
                                  Text(p.phone,
                                      style: TextStyle(
                                          fontSize: 12, color: Colors.grey.shade600)),
                                  Text(p.institution,
                                      style: TextStyle(
                                          fontSize: 12, color: Colors.grey.shade600)),
                                ],
                              ),
                            ),
                            TextButton(
                              onPressed: () => _confirmRemove(context, p.id, p.name),
                              style: TextButton.styleFrom(
                                foregroundColor: Colors.red,
                                padding: EdgeInsets.zero,
                                minimumSize: const Size(48, 32),
                              ),
                              child: const Text('Hapus', style: TextStyle(fontSize: 12)),
                            ),
                          ],
                        ),
                      );
                    },
                  ),
                ),
        ],
      ),
    );
  }

  void _confirmRemove(BuildContext context, String participantId, String name) {
    showDialog(
      context: context,
      builder: (_) => AlertDialog(
        shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(16)),
        title: const Text('Hapus Peserta?'),
        content: Text('Data "$name" akan dihapus dari kegiatan ini.'),
        actions: [
          TextButton(onPressed: () => Navigator.pop(context), child: const Text('Batal')),
          ElevatedButton(
            style: ElevatedButton.styleFrom(
                backgroundColor: Colors.red, foregroundColor: Colors.white),
            onPressed: () {
              context.read<AppProvider>().removeParticipant(participantId, activity.id);
              Navigator.pop(context);
            },
            child: const Text('Hapus'),
          ),
        ],
      ),
    );
  }
}
```
```dart
import 'package:flutter/material.dart';
import 'package:provider/provider.dart';
import '../models/activity.dart';
import '../providers/app_provider.dart';

class RegisterScreen extends StatefulWidget {
  final Activity activity;
  const RegisterScreen({super.key, required this.activity});

  @override
  State<RegisterScreen> createState() => _RegisterScreenState();
}

class _RegisterScreenState extends State<RegisterScreen> {
  final _formKey = GlobalKey<FormState>();
  final _nameController = TextEditingController();
  final _phoneController = TextEditingController();
  final _emailController = TextEditingController();
  final _institutionController = TextEditingController();
  bool _isLoading = false;

  @override
  void dispose() {
    _nameController.dispose();
    _phoneController.dispose();
    _emailController.dispose();
    _institutionController.dispose();
    super.dispose();
  }

  String? _validateEmail(String? value) {
    if (value == null || value.trim().isEmpty) {
      return 'Email wajib diisi';
    }
    final emailRegex = RegExp(r'^[a-zA-Z0-9._%+\-]+@[a-zA-Z0-9.\-]+\.[a-zA-Z]{2,}$');
    if (!emailRegex.hasMatch(value.trim())) {
      return 'Format email tidak valid (contoh: nama@gmail.com)';
    }
    return null;
  }

  String? _validatePhone(String? value) {
    if (value == null || value.trim().isEmpty) {
      return 'Nomor WhatsApp wajib diisi';
    }
    final trimmed = value.trim().replaceAll(' ', '').replaceAll('-', '');
    final phoneRegex = RegExp(r'^(\+62|62|0)[0-9]{9,12}$');
    if (!phoneRegex.hasMatch(trimmed)) {
      return 'Format nomor tidak valid (contoh: 08123456789)';
    }
    return null;
  }

  void _submit() async {
    if (!_formKey.currentState!.validate()) return;
    setState(() => _isLoading = true);

    // Simpan semua referensi context SEBELUM await
    final appProvider = context.read<AppProvider>();
    final scaffoldMessenger = ScaffoldMessenger.of(context);
    final navigator = Navigator.of(context);

    await Future.delayed(const Duration(milliseconds: 500));

    final success = appProvider.registerParticipant(
      activityId: widget.activity.id,
      name: _nameController.text.trim(),
      phone: _phoneController.text.trim(),
      email: _emailController.text.trim(),
      institution: _institutionController.text.trim(),
    );

    if (!mounted) return;
    setState(() => _isLoading = false);

    if (success) {
      showDialog(
        context: context,
        barrierDismissible: false,
        builder: (_) => AlertDialog(
          shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(16)),
          content: Column(
            mainAxisSize: MainAxisSize.min,
            children: [
              const Icon(Icons.check_circle, color: Color(0xFF1565C0), size: 64),
              const SizedBox(height: 16),
              const Text(
                'Pendaftaran Berhasil!',
                style: TextStyle(fontSize: 18, fontWeight: FontWeight.bold),
              ),
              const SizedBox(height: 8),
              Text(
                'Kamu telah terdaftar sebagai relawan di kegiatan "${widget.activity.title}". Sampai jumpa di lokasi!',
                textAlign: TextAlign.center,
                style: const TextStyle(color: Colors.grey, fontSize: 13),
              ),
            ],
          ),
          actions: [
            ElevatedButton(
              style: ElevatedButton.styleFrom(
                backgroundColor: const Color(0xFF1565C0),
                foregroundColor: Colors.white,
                minimumSize: const Size(double.infinity, 44),
                shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(10)),
              ),
              onPressed: () {
                navigator.pop();
                navigator.pop();
              },
              child: const Text('Kembali ke Detail Kegiatan'),
            ),
          ],
        ),
      );
    } else {
      scaffoldMessenger.showSnackBar(
        SnackBar(
          content: const Text('Slot penuh! Pendaftaran tidak dapat dilakukan.'),
          backgroundColor: Colors.red.shade700,
          behavior: SnackBarBehavior.floating,
          shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(10)),
        ),
      );
    }
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: const Color(0xFFF0F4FF),
      appBar: AppBar(
        backgroundColor: const Color(0xFF1565C0),
        foregroundColor: Colors.white,
        title: const Text('Form Pendaftaran'),
        elevation: 0,
      ),
      body: SingleChildScrollView(
        padding: const EdgeInsets.all(16),
        child: Form(
          key: _formKey,
          child: Column(
            crossAxisAlignment: CrossAxisAlignment.start,
            children: [
              // Info kegiatan
              Container(
                width: double.infinity,
                padding: const EdgeInsets.all(14),
                decoration: BoxDecoration(
                  color: const Color(0xFF1565C0).withValues(alpha: 0.07),
                  borderRadius: BorderRadius.circular(12),
                  border: Border.all(color: const Color(0xFF1565C0).withValues(alpha: 0.25)),
                ),
                child: Column(
                  crossAxisAlignment: CrossAxisAlignment.start,
                  children: [
                    const Text('Mendaftar untuk:', style: TextStyle(color: Colors.grey, fontSize: 12)),
                    const SizedBox(height: 4),
                    Text(widget.activity.title,
                        style: const TextStyle(fontWeight: FontWeight.bold, fontSize: 15)),
                    const SizedBox(height: 2),
                    Text(widget.activity.date,
                        style: const TextStyle(color: Colors.grey, fontSize: 12)),
                  ],
                ),
              ),

              const SizedBox(height: 20),
              const Text('Data Diri', style: TextStyle(fontWeight: FontWeight.bold, fontSize: 16)),
              const SizedBox(height: 14),

              _buildField(
                controller: _nameController,
                label: 'Nama Lengkap',
                hint: 'Masukkan nama lengkap',
                validator: (v) => v == null || v.trim().isEmpty ? 'Nama wajib diisi' : null,
              ),
              const SizedBox(height: 14),

              _buildField(
                controller: _phoneController,
                label: 'Nomor WhatsApp',
                hint: 'Contoh: 08123456789',
                keyboardType: TextInputType.phone,
                validator: _validatePhone,
              ),
              const SizedBox(height: 14),

              _buildField(
                controller: _emailController,
                label: 'Email',
                hint: 'Contoh: nama@gmail.com',
                keyboardType: TextInputType.emailAddress,
                validator: _validateEmail,
              ),
              const SizedBox(height: 14),

              _buildField(
                controller: _institutionController,
                label: 'Asal Instansi / Kampus',
                hint: 'Contoh: Universitas Mulawarman',
                validator: (v) => v == null || v.trim().isEmpty ? 'Asal instansi wajib diisi' : null,
              ),

              const SizedBox(height: 28),

              SizedBox(
                width: double.infinity,
                height: 52,
                child: ElevatedButton(
                  onPressed: _isLoading ? null : _submit,
                  style: ElevatedButton.styleFrom(
                    backgroundColor: const Color(0xFF1565C0),
                    foregroundColor: Colors.white,
                    shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(12)),
                  ),
                  child: _isLoading
                      ? const SizedBox(
                          width: 22,
                          height: 22,
                          child: CircularProgressIndicator(color: Colors.white, strokeWidth: 2.5),
                        )
                      : const Text(
                          'Konfirmasi Pendaftaran',
                          style: TextStyle(fontSize: 16, fontWeight: FontWeight.bold),
                        ),
                ),
              ),
              const SizedBox(height: 20),
            ],
          ),
        ),
      ),
    );
  }

  Widget _buildField({
    required TextEditingController controller,
    required String label,
    required String hint,
    TextInputType? keyboardType,
    String? Function(String?)? validator,
  }) {
    return Column(
      crossAxisAlignment: CrossAxisAlignment.start,
      children: [
        Text(label, style: const TextStyle(fontWeight: FontWeight.w600, fontSize: 13)),
        const SizedBox(height: 6),
        TextFormField(
          controller: controller,
          keyboardType: keyboardType,
          validator: validator,
          autovalidateMode: AutovalidateMode.onUserInteraction,
          decoration: InputDecoration(
            hintText: hint,
            hintStyle: TextStyle(color: Colors.grey.shade400, fontSize: 13),
            filled: true,
            fillColor: Colors.white,
            border: OutlineInputBorder(
                borderRadius: BorderRadius.circular(12),
                borderSide: BorderSide(color: Colors.grey.shade300)),
            enabledBorder: OutlineInputBorder(
                borderRadius: BorderRadius.circular(12),
                borderSide: BorderSide(color: Colors.grey.shade300)),
            focusedBorder: OutlineInputBorder(
                borderRadius: BorderRadius.circular(12),
                borderSide: const BorderSide(color: Color(0xFF1565C0), width: 2)),
            errorBorder: OutlineInputBorder(
                borderRadius: BorderRadius.circular(12),
                borderSide: const BorderSide(color: Colors.red, width: 1.5)),
            focusedErrorBorder: OutlineInputBorder(
                borderRadius: BorderRadius.circular(12),
                borderSide: const BorderSide(color: Colors.red, width: 2)),
            contentPadding: const EdgeInsets.symmetric(horizontal: 14, vertical: 14),
          ),
        ),
      ],
    );
  }
}
```
```dart
import 'package:flutter/material.dart';
import '../models/activity.dart';

class ActivityCard extends StatelessWidget {
  final Activity activity;
  final VoidCallback onTap;
  final VoidCallback? onRegister;

  const ActivityCard({
    super.key,
    required this.activity,
    required this.onTap,
    this.onRegister,
  });

  List<Color> get _gradientColors {
    switch (activity.category) {
      case 'Lingkungan':
        return [const Color(0xFF0D47A1), const Color(0xFF64B5F6)];
      case 'Kesehatan':
        return [const Color(0xFFB71C1C), const Color(0xFFEF9A9A)];
      case 'Pendidikan':
        return [const Color(0xFF0D47A1), const Color(0xFF64B5F6)];
      case 'Sosial':
        return [const Color(0xFF4A148C), const Color(0xFFCE93D8)];
      default:
        return [const Color(0xFF263238), const Color(0xFF90A4AE)];
    }
  }

  IconData get _categoryIcon {
    switch (activity.category) {
      case 'Lingkungan': return Icons.park;
      case 'Kesehatan':  return Icons.favorite;
      case 'Pendidikan': return Icons.school;
      case 'Sosial':     return Icons.people;
      default:           return Icons.volunteer_activism;
    }
  }

  @override
  Widget build(BuildContext context) {
    final slotPercent = activity.maxParticipants > 0
        ? activity.registeredCount / activity.maxParticipants
        : 0.0;

    return Container(
      margin: const EdgeInsets.only(bottom: 16),
      decoration: BoxDecoration(
        color: Colors.white,
        borderRadius: BorderRadius.circular(20),
        boxShadow: [
          BoxShadow(
            color: _gradientColors[0].withValues(alpha: 0.15),
            blurRadius: 12,
            offset: const Offset(0, 4),
          ),
        ],
      ),
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.start,
        children: [
          // Banner
          GestureDetector(
            onTap: onTap,
            child: ClipRRect(
              borderRadius: const BorderRadius.only(
                topLeft: Radius.circular(20),
                topRight: Radius.circular(20),
              ),
              child: Container(
                height: 155,
                width: double.infinity,
                decoration: BoxDecoration(
                  gradient: LinearGradient(
                    begin: Alignment.topLeft,
                    end: Alignment.bottomRight,
                    colors: _gradientColors,
                  ),
                ),
                child: Stack(
                  children: [
                    // Decorative circles
                    Positioned(
                      right: -24, top: -24,
                      child: Container(
                        width: 130, height: 130,
                        decoration: BoxDecoration(
                          shape: BoxShape.circle,
                          color: Colors.white.withValues(alpha: 0.08),
                        ),
                      ),
                    ),
                    Positioned(
                      right: 24, bottom: -36,
                      child: Container(
                        width: 100, height: 100,
                        decoration: BoxDecoration(
                          shape: BoxShape.circle,
                          color: Colors.white.withValues(alpha: 0.08),
                        ),
                      ),
                    ),
                    Positioned(
                      left: -16, bottom: -16,
                      child: Container(
                        width: 80, height: 80,
                        decoration: BoxDecoration(
                          shape: BoxShape.circle,
                          color: Colors.white.withValues(alpha: 0.06),
                        ),
                      ),
                    ),
                    // Category badge
                    Positioned(
                      top: 12, left: 12,
                      child: Container(
                        padding: const EdgeInsets.symmetric(horizontal: 10, vertical: 5),
                        decoration: BoxDecoration(
                          color: Colors.white.withValues(alpha: 0.22),
                          borderRadius: BorderRadius.circular(20),
                          border: Border.all(color: Colors.white30),
                        ),
                        child: Row(
                          mainAxisSize: MainAxisSize.min,
                          children: [
                            Icon(_categoryIcon, size: 12, color: Colors.white),
                            const SizedBox(width: 5),
                            Text(
                              activity.category,
                              style: const TextStyle(
                                color: Colors.white,
                                fontSize: 12,
                                fontWeight: FontWeight.bold,
                              ),
                            ),
                          ],
                        ),
                      ),
                    ),
                    // PENUH badge
                    if (activity.isFull)
                      Positioned(
                        top: 12, right: 12,
                        child: Container(
                          padding: const EdgeInsets.symmetric(horizontal: 10, vertical: 5),
                          decoration: BoxDecoration(
                            color: Colors.red.shade700,
                            borderRadius: BorderRadius.circular(20),
                          ),
                          child: const Text(
                            'PENUH',
                            style: TextStyle(
                              color: Colors.white,
                              fontSize: 11,
                              fontWeight: FontWeight.bold,
                            ),
                          ),
                        ),
                      ),
                    // Big center icon
                    Center(
                      child: Icon(_categoryIcon, size: 68,
                          color: Colors.white.withValues(alpha: 0.22)),
                    ),
                    // Title di bawah banner
                    Positioned(
                      bottom: 12, left: 14, right: 14,
                      child: Text(
                        activity.title,
                        style: const TextStyle(
                          color: Colors.white,
                          fontSize: 17,
                          fontWeight: FontWeight.bold,
                          shadows: [Shadow(blurRadius: 8, color: Colors.black38)],
                        ),
                        maxLines: 2,
                        overflow: TextOverflow.ellipsis,
                      ),
                    ),
                  ],
                ),
              ),
            ),
          ),

          // Body info
          GestureDetector(
            onTap: onTap,
            child: Padding(
              padding: const EdgeInsets.fromLTRB(14, 12, 14, 0),
              child: Column(
                crossAxisAlignment: CrossAxisAlignment.start,
                children: [
                  Row(
                    children: [
                      Icon(Icons.business_outlined, size: 14, color: Colors.grey.shade500),
                      const SizedBox(width: 5),
                      Expanded(
                        child: Text(
                          activity.organizer,
                          style: TextStyle(
                            color: Colors.grey.shade600,
                            fontSize: 12,
                            fontWeight: FontWeight.w500,
                          ),
                          overflow: TextOverflow.ellipsis,
                        ),
                      ),
                    ],
                  ),
                  const SizedBox(height: 8),
                  Text(
                    activity.description,
                    style: const TextStyle(fontSize: 13, color: Color(0xFF444444), height: 1.45),
                    maxLines: 3,
                    overflow: TextOverflow.ellipsis,
                  ),
                  const SizedBox(height: 10),
                  Row(
                    children: [
                      Icon(Icons.calendar_today_outlined, size: 13, color: _gradientColors[0]),
                      const SizedBox(width: 5),
                      Text(
                        activity.date,
                        style: TextStyle(fontSize: 12, color: _gradientColors[0], fontWeight: FontWeight.w600),
                      ),
                      const SizedBox(width: 12),
                      Icon(Icons.access_time_outlined, size: 13, color: Colors.grey.shade500),
                      const SizedBox(width: 5),
                      Expanded(
                        child: Text(
                          activity.time,
                          style: TextStyle(fontSize: 12, color: Colors.grey.shade600),
                          overflow: TextOverflow.ellipsis,
                        ),
                      ),
                    ],
                  ),
                  const SizedBox(height: 5),
                  Row(
                    children: [
                      Icon(Icons.location_on_outlined, size: 13, color: Colors.grey.shade500),
                      const SizedBox(width: 5),
                      Expanded(
                        child: Text(
                          activity.location,
                          style: TextStyle(fontSize: 12, color: Colors.grey.shade600),
                          overflow: TextOverflow.ellipsis,
                        ),
                      ),
                    ],
                  ),
                  const SizedBox(height: 10),
                  Row(
                    mainAxisAlignment: MainAxisAlignment.spaceBetween,
                    children: [
                      Text('Slot Tersedia', style: TextStyle(fontSize: 11, color: Colors.grey.shade500)),
                      Text(
                        '${activity.availableSlots} / ${activity.maxParticipants} relawan',
                        style: TextStyle(
                          fontSize: 11,
                          fontWeight: FontWeight.bold,
                          color: slotPercent > 0.8 ? Colors.red : _gradientColors[0],
                        ),
                      ),
                    ],
                  ),
                  const SizedBox(height: 5),
                  ClipRRect(
                    borderRadius: BorderRadius.circular(4),
                    child: LinearProgressIndicator(
                      value: slotPercent.toDouble(),
                      backgroundColor: Colors.grey.shade100,
                      valueColor: AlwaysStoppedAnimation(
                        slotPercent > 0.8 ? Colors.red : _gradientColors[0],
                      ),
                      minHeight: 6,
                    ),
                  ),
                ],
              ),
            ),
          ),

          // Buttons
          Padding(
            padding: const EdgeInsets.fromLTRB(14, 12, 14, 14),
            child: Row(
              children: [
                Expanded(
                  child: OutlinedButton(
                    onPressed: onTap,
                    style: OutlinedButton.styleFrom(
                      side: BorderSide(color: _gradientColors[0]),
                      foregroundColor: _gradientColors[0],
                      shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(10)),
                      padding: const EdgeInsets.symmetric(vertical: 11),
                    ),
                    child: const Text('Detail', style: TextStyle(fontSize: 13, fontWeight: FontWeight.w600)),
                  ),
                ),
                const SizedBox(width: 10),
                Expanded(
                  flex: 2,
                  child: ElevatedButton.icon(
                    onPressed: activity.isFull ? null : onRegister,
                    icon: Icon(
                      activity.isFull ? Icons.lock_outline : Icons.how_to_reg,
                      size: 16,
                    ),
                    label: Text(
                      activity.isFull ? 'Slot Penuh' : 'Daftar Sekarang',
                      style: const TextStyle(fontSize: 13, fontWeight: FontWeight.bold),
                    ),
                    style: ElevatedButton.styleFrom(
                      backgroundColor: activity.isFull ? Colors.grey.shade300 : _gradientColors[0],
                      foregroundColor: Colors.white,
                      disabledBackgroundColor: Colors.grey.shade200,
                      disabledForegroundColor: Colors.grey.shade500,
                      elevation: 0,
                      shape: RoundedRectangleBorder(borderRadius: BorderRadius.circular(10)),
                      padding: const EdgeInsets.symmetric(vertical: 11),
                    ),
                  ),
                ),
              ],
            ),
          ),
        ],
      ),
    );
  }
}
```
## MAIN
```dart
import 'package:flutter/material.dart';
import 'package:flutter_localizations/flutter_localizations.dart';
import 'package:provider/provider.dart';
import 'providers/app_provider.dart';
import 'screens/home_screen.dart';

void main() {
  runApp(
    ChangeNotifierProvider(
      create: (_) => AppProvider(),
      child: const GoVolunteerApp(),
    ),
  );
}

class GoVolunteerApp extends StatelessWidget {
  const GoVolunteerApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'GoVolunteer',
      debugShowCheckedModeBanner: false,
      // Localization untuk kalender bahasa Indonesia
      localizationsDelegates: const [
        GlobalMaterialLocalizations.delegate,
        GlobalWidgetsLocalizations.delegate,
        GlobalCupertinoLocalizations.delegate,
      ],
      supportedLocales: const [
        Locale('id', 'ID'), // Bahasa Indonesia
        Locale('en', 'US'),
      ],
      locale: const Locale('id', 'ID'),
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: const Color (0xFF1565C0)),
        useMaterial3: true,
        fontFamily: 'Roboto',
      ),
      home: const HomeScreen(),
    );
  }
}
```
# DOKUMENTASI APLIKASI
1. Tampilan Home yang belum memiliki kegiatan yang tersedia, pada ujung kanan atas ada icon untuk admin panel yang khusus diakses oleh admin. Masih belum ada sistem login untuk user atau pengguna. 
<img width="1919" height="1122" alt="Cuplikan layar 2026-02-28 124939" src="https://github.com/user-attachments/assets/cd62dc03-3e7d-4d62-9525-58217ed7df85" />
2. Tampilan admin panel, admin dapat melihat statistik dari total kegiatan dan total relawan. Di ujung kanan bawah ada tombol tambah kegiatan untuk menambahkan kegiatan.
<img width="1917" height="1122" alt="Cuplikan layar 2026-02-28 124957" src="https://github.com/user-attachments/assets/1e45d947-a1d1-418f-976c-746b9d87ea7d" />
3. Di halaman tambah kegiatan, terdapat beberapa field yang harus diisi oleh admin seperti nama kegiatan, organisasi yang menyelenggarakan, waktu, deskripsinya dll.
<img width="1915" height="1123" alt="Cuplikan layar 2026-02-28 125214" src="https://github.com/user-attachments/assets/86d9d1d0-f6b4-44dc-b7d0-11d29a101f34" />
<img width="1918" height="1130" alt="Cuplikan layar 2026-02-28 125225" src="https://github.com/user-attachments/assets/05704324-9b0d-4bd7-b5dc-fc6a2e2228b6" />
4. Kegiatan berhasil di tambahkan dan statistiknya secara otomatis terupdate berdasarkan kegiatan yang di inputkan.
<img width="1915" height="1130" alt="Cuplikan layar 2026-02-28 125233" src="https://github.com/user-attachments/assets/2e10510c-e7ff-43da-98be-059cc0b468f6" />
5. Di halaman home juga langsung terupdate kegiatannya yang dapat dilihat oleh user nantinya, dan di card kegiatannya terdapat keterangan dari kegiatan atau detail, dan pendaftaran.
<img width="1919" height="1128" alt="Cuplikan layar 2026-02-28 125243" src="https://github.com/user-attachments/assets/d793dead-37e2-4ee5-bfbb-ad8ab82c8900" />
6. Tampilan dari button detail adalah menampilkan detail dari kegiatan yang sedang berlangsung.
<img width="1914" height="1123" alt="Cuplikan layar 2026-02-28 125255" src="https://github.com/user-attachments/assets/c06aa690-cda8-4557-a54a-e372de4d6762" />
7. form pendaftaran memiliki beberapa field seperti nama pendaftar, nomer, email dan asal instansi yang dapat diisi oleh masyakarat yang berasal dari instansi tertentu atau individu. Jika individu bisa mengisi dengan "-".
<img width="1917" height="1128" alt="Cuplikan layar 2026-02-28 125331" src="https://github.com/user-attachments/assets/4136f7b0-7569-45d7-a536-288139e9cc91" />
8. Notifikasi pop up saat pendaftar berhasil mendaftar ke kegiatan.
<img width="1919" height="1130" alt="Cuplikan layar 2026-02-28 125340" src="https://github.com/user-attachments/assets/f6d7879b-9e15-4fd5-96ae-54f13480dd6b" />
9. Tampilan home yang secara otomatis terupdate untuk jumlah pendaftar, yang sebelumnya 50 menjadi 49. Dan progress bar juga terisi sesuai jumlah pendaftar.
<img width="1918" height="1128" alt="Cuplikan layar 2026-02-28 125348" src="https://github.com/user-attachments/assets/87cc1de9-e83d-4744-8df4-5ec528b215ec" />
10. statistik di Admin panel juga terupdate untuk relawan yang mendaftar di kegiatan.
<img width="1916" height="1126" alt="Cuplikan layar 2026-02-28 125400" src="https://github.com/user-attachments/assets/dc0064fa-8907-4a07-bbf7-4b98a268bbf2" />
11. Admin dapat melihat detail peserta di kegiatan dan dapat menghapus peserta.
<img width="1919" height="1123" alt="Cuplikan layar 2026-02-28 125417" src="https://github.com/user-attachments/assets/fffe6957-3251-431b-a3e4-8faeefe2ad5f" />
12. Admin dapat mengedit informasi kegiatan dan menyimpan perubahannya.
<img width="1918" height="1120" alt="Cuplikan layar 2026-02-28 125429" src="https://github.com/user-attachments/assets/aa3196d5-770b-4b1a-a8de-ea7f7fc18e7e" />
