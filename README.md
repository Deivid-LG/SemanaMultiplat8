
# Codigo main dart

´´´

	import 'package:flutter/material.dart';
	import 'package:google_fonts/google_fonts.dart';
	void main() {
	  runApp(const MyApp());
	}

		class MyApp extends StatelessWidget {
	  const MyApp({Key? key}) : super(key: key);

	  @override
	  Widget build(BuildContext context) {
	    return MaterialApp(
	      debugShowCheckedModeBanner: false,
	      title: 'Mi Aplicación',
	      theme: ThemeData(
	        primarySwatch: Colors.blue,
	        colorScheme: ColorScheme.fromSeed(
	          seedColor: Colors.blue,
	          brightness: Brightness.light,
	        ),
	        textTheme: GoogleFonts.interTextTheme(),
	        elevatedButtonTheme: ElevatedButtonThemeData(
	          style: ElevatedButton.styleFrom(
	            foregroundColor: Colors.white,
	            backgroundColor: Colors.blue,
	            padding: const EdgeInsets.symmetric(horizontal: 32, vertical: 16),
	            shape: RoundedRectangleBorder(
	              borderRadius: BorderRadius.circular(14),
	            ),
	            elevation: 2,
	          ),
	        ),
	        inputDecorationTheme: InputDecorationTheme(
	          filled: true,
	          fillColor: Colors.white,
	          border: OutlineInputBorder(
	            borderRadius: BorderRadius.circular(14),
	            borderSide: BorderSide.none,
	          ),
	          enabledBorder: OutlineInputBorder(
	            borderRadius: BorderRadius.circular(14),
	            borderSide: BorderSide(color: Colors.blue.shade100, width: 1.5),
	          ),
	          focusedBorder: OutlineInputBorder(
	            borderRadius: BorderRadius.circular(14),
	            borderSide: const BorderSide(color: Colors.blue, width: 1.5),
	          ),
	          contentPadding: const EdgeInsets.symmetric(horizontal: 20, vertical: 16),
	          floatingLabelBehavior: FloatingLabelBehavior.never,
	        ),
	      ),
	      initialRoute: "/login",
	      routes: {
	        "/login": (context) => const LoginPage(),
	        "/main": (context) => const MainPage(),
	        "/faq": (context) => const FAQPage(),
	        "/register": (context) => const RegisterPage(),
	        "/calculator": (context) => const CalculatorPage(),
	      },
	    );
	  }
	}

	// Página de Login - Simplificada y más bonita
	class LoginPage extends StatelessWidget {
	  const LoginPage({Key? key}) : super(key: key);

	  @override
	  Widget build(BuildContext context) {
	    return Scaffold(
	      backgroundColor: Colors.grey.shade50,
	      body: SafeArea(
	        child: Center(
	          child: SingleChildScrollView(
	            padding: const EdgeInsets.all(24.0),
	            child: Column(
	              mainAxisAlignment: MainAxisAlignment.center,
	              children: [
	                // Logo mejorado
	                Container(
	                  height: 100,
	                  width: 100,
	                  decoration: BoxDecoration(
	                    gradient: LinearGradient(
	                      colors: [Colors.blue.shade400, Colors.blue.shade700],
	                      begin: Alignment.topLeft,
	                      end: Alignment.bottomRight,
	                    ),
	                    shape: BoxShape.circle,
                    boxShadow: [
                      BoxShadow(
                        color: Colors.blue.shade200.withOpacity(0.5),
                        blurRadius: 15,
                        spreadRadius: 5,
                      ),
                    ],
                  ),
                  child: const Icon(
                    Icons.person,
                    size: 50,
                    color: Colors.white,
                  ),
                ),
                const SizedBox(height: 40),
                // Título simplificado
                Text(
                  "Bienvenido",
                  style: TextStyle(
                    fontSize: 28,
                    fontWeight: FontWeight.bold,
                    color: Colors.blue.shade800,
                  ),
                ),
                const SizedBox(height: 36),
                // Campos de login simplificados
                TextField(
                  decoration: InputDecoration(
                    hintText: 'Usuario',
                    prefixIcon: Icon(Icons.person, color: Colors.blue.shade400),
                    contentPadding: const EdgeInsets.all(18),
                  ),
                ),
                const SizedBox(height: 16),
                TextField(
                  obscureText: true,
                  decoration: InputDecoration(
                    hintText: 'Contraseña',
                    prefixIcon: Icon(Icons.lock, color: Colors.blue.shade400),
                    contentPadding: const EdgeInsets.all(18),
                  ),
                ),
                const SizedBox(height: 8),
                Align(
                  alignment: Alignment.centerRight,
                  child: TextButton(
                    onPressed: () {},
                    child: Text(
                      "¿Olvidaste tu contraseña?",
                      style: TextStyle(color: Colors.blue.shade600),
                    ),
                  ),
                ),
                const SizedBox(height: 32),
                // Botón más atractivo
                SizedBox(
                  width: double.infinity,
                  height: 55,
                  child: ElevatedButton(
                    onPressed: () {
                      Navigator.pushReplacementNamed(context, "/main");
                    },
                    style: ElevatedButton.styleFrom(
                      shape: RoundedRectangleBorder(
                        borderRadius: BorderRadius.circular(14),
                      ),
                      elevation: 3,
                      shadowColor: Colors.blue.shade300,
                    ),
                    child: const Text(
                      "Iniciar Sesión",
                      style: TextStyle(fontSize: 16, fontWeight: FontWeight.w600),
                    ),
                  ),
                ),
                const SizedBox(height: 24),
                Row(
                  mainAxisAlignment: MainAxisAlignment.center,
                  children: [
                    Text(
                      "¿No tienes una cuenta?",
                      style: TextStyle(color: Colors.grey.shade700),
                    ),
                    TextButton(
                      onPressed: () {
                        Navigator.pushNamed(context, "/register");
                      },
                      child: Text(
                        "Regístrate",
                        style: TextStyle(
                          color: Colors.blue.shade700,
                          fontWeight: FontWeight.bold,
                        ),
                      ),
                    ),
                  ],
                ),
              ],
            ),
          ),
        ),
      ),
    );
	  }
	}

	// Página Principal - Rediseñada más atractiva
	class MainPage extends StatelessWidget {
	  const MainPage({Key? key}) : super(key: key);

	  @override
	  Widget build(BuildContext context) {
	    return Scaffold(
	      backgroundColor: Colors.grey.shade100,
	      appBar: AppBar(
	        title: const Text("Mi Aplicación"),
	        backgroundColor: Colors.blue,
	        foregroundColor: Colors.white,
	        elevation: 0,
	        centerTitle: true,
	        actions: [
	          IconButton(
	            icon: const Icon(Icons.logout),
	            onPressed: () {
	              Navigator.pushReplacementNamed(context, "/login");
	            },
	          ),
	        ],
	      ),
	      body: Container(
	        decoration: BoxDecoration(
	          gradient: LinearGradient(
	            begin: Alignment.topCenter,
	            end: Alignment.bottomCenter,
	            colors: [Colors.blue.withOpacity(0.1), Colors.grey.shade50],
	          ),
	        ),
	        child: Padding(
	          padding: const EdgeInsets.all(24.0),
	          child: Column(
	            crossAxisAlignment: CrossAxisAlignment.start,
	            children: [
	              // Encabezado mejorado
	              Text(
	                "¡Hola!",
	                style: TextStyle(
	                  fontSize: 32,
	                  fontWeight: FontWeight.bold,
	                  color: Colors.blue.shade900,
	                ),
	              ),
	              const Text(
	                "¿Qué deseas hacer hoy?",
	                style: TextStyle(
	                  fontSize: 18,
	                  color: Colors.grey,
	                  fontWeight: FontWeight.w500,
	                ),
	              ),
	              const SizedBox(height: 36),
	              // Menú principal rediseñado - Tarjetas más atractivas
	              Expanded(
	                child: GridView.count(
	                  crossAxisCount: 1,
	                  childAspectRatio: 3.2,
	                  mainAxisSpacing: 20,
	                  children: [
	                    MenuOptionCard(
	                      title: "Preguntas Frecuentes",
	                      subtitle: "Resuelve tus dudas",
	                      icon: Icons.help_outline,
	                      color: Colors.purple,
	                      onTap: () {
	                        Navigator.pushNamed(context, "/faq");
	                      },
	                    ),
	                    MenuOptionCard(
	                      title: "Registro",
	                      subtitle: "Crea una cuenta nueva",
	                      icon: Icons.app_registration,
	                      color: Colors.green,
	                      onTap: () {
	                        Navigator.pushNamed(context, "/register");
	                      },
	                    ),
	                    MenuOptionCard(
	                      title: "Calculadora",
	                      subtitle: "Realiza operaciones simples",
	                      icon: Icons.calculate_outlined,
	                      color: Colors.orange,
	                      onTap: () {
	                        Navigator.pushNamed(context, "/calculator");
	                      },
	                    ),
	                  ],
	                ),
	              ),
	            ],
	          ),
	        ),
	      ),
	    );
	  }
	}

	// Componente Card para menú principal - Rediseñado
	class MenuOptionCard extends StatelessWidget {
	  final String title;
	  final String subtitle;
	  final IconData icon;
	  final Color color;
	  final VoidCallback onTap;

	  const MenuOptionCard({
	    Key? key,
	    required this.title,
	    required this.subtitle,
	    required this.icon,
	    required this.color,
	    required this.onTap,
	  }) : super(key: key);

	  @override
	  Widget build(BuildContext context) {
	    return Card(
	      elevation: 4,
	      shape: RoundedRectangleBorder(
	        borderRadius: BorderRadius.circular(20),
	      ),
	      shadowColor: color.withOpacity(0.3),
	      child: InkWell(
	        onTap: onTap,
	        borderRadius: BorderRadius.circular(20),
	        child: Padding(
	          padding: const EdgeInsets.symmetric(horizontal: 20, vertical: 16),
	          child: Row(
	            children: [
	              // Ícono más atractivo
	              Container(
	                padding: const EdgeInsets.all(14),
	                decoration: BoxDecoration(
	                  gradient: LinearGradient(
	                    colors: [color.withOpacity(0.7), color],
	                    begin: Alignment.topLeft,
	                    end: Alignment.bottomRight,
	                  ),
	                  borderRadius: BorderRadius.circular(16),
	                  boxShadow: [
	                    BoxShadow(
	                      color: color.withOpacity(0.3),
	                      blurRadius: 8,
	                      offset: const Offset(0, 3),
	                    ),
	                  ],
	                ),
	                child: Icon(
	                  icon,
	                  size: 30,
	                  color: Colors.white,
	                ),
	              ),
	              const SizedBox(width: 20),
	              // Contenido
	              Expanded(
	                child: Column(
	                  crossAxisAlignment: CrossAxisAlignment.start,
	                  mainAxisAlignment: MainAxisAlignment.center,
	                  children: [
	                    Text(
	                      title,
	                      style: const TextStyle(
	                        fontSize: 18,
	                        fontWeight: FontWeight.bold,
	                      ),
	                    ),
	                    const SizedBox(height: 4),
	                    Text(
	                      subtitle,
	                      style: TextStyle(
	                        fontSize: 14,
	                        color: Colors.grey.shade600,
	                      ),
	                    ),
	                  ],
	                ),
	              ),
	              Icon(
	                Icons.arrow_forward_ios,
	                size: 16,
	                color: color,
	              ),
	            ],
	          ),
	        ),
	      ),
	    );
	  }
	}

	// Página de FAQ - Rediseñada
	class FAQPage extends StatelessWidget {
	  const FAQPage({Key? key}) : super(key: key);

	  @override
	  Widget build(BuildContext context) {
	    return Scaffold(
	      backgroundColor: Colors.grey.shade50,
	      appBar: AppBar(
	        title: const Text("Preguntas Frecuentes"),
	        backgroundColor: Colors.blue,
	        foregroundColor: Colors.white,
	        elevation: 2,
	        centerTitle: true,
	      ),
	      body: Padding(
	        padding: const EdgeInsets.all(16.0),
	        child: ListView.builder(
	          itemCount: faqList.length,
	          itemBuilder: (context, index) {
	            return Padding(
	              padding: const EdgeInsets.only(bottom: 12.0),
	              child: Card(
	                elevation: 2,
	                shadowColor: Colors.blue.shade100,
	                shape: RoundedRectangleBorder(
	                  borderRadius: BorderRadius.circular(16),
	                ),
	                child: ClipRRect(
	                  borderRadius: BorderRadius.circular(16),
	                  child: ExpansionTile(
	                    collapsedBackgroundColor: Colors.white,
	                    backgroundColor: Colors.blue.shade50,
	                    leading: CircleAvatar(
	                      backgroundColor: Colors.blue.shade100,
	                      child: Text(
	                        "${index + 1}",
	                        style: TextStyle(
	                          color: Colors.blue.shade800,
	                          fontWeight: FontWeight.bold,
	                        ),
	                      ),
	                    ),
	                    iconColor: Colors.blue,
	                    collapsedIconColor: Colors.blue.shade300,
	                    title: Text(
	                      faqList[index].question,
	                      style: const TextStyle(
	                        fontWeight: FontWeight.w600,
	                        fontSize: 16,
	                      ),
	                    ),
	                    children: [
	                      Padding(
	                        padding: const EdgeInsets.symmetric(
	                          horizontal: 20.0,
	                          vertical: 16.0,
	                        ),
	                        child: Text(
	                          faqList[index].answer,
	                          style: TextStyle(
	                            fontSize: 15.0,
	                            height: 1.5,
	                            color: Colors.grey.shade800,
	                          ),
	                        ),
	                      ),
	                    ],
	                  ),
	                ),
	              ),
	            );
	          },
	        ),
	      ),
	      floatingActionButton: FloatingActionButton.extended(
	        onPressed: () {
	          Navigator.pushReplacementNamed(context, "/main");
	        },
	        backgroundColor: Colors.blue,
	        icon: const Icon(Icons.home),
	        label: const Text("Volver al Inicio"),
	      ),
	    );
	  }
	}

	// Página de Registro - Rediseñada
	class RegisterPage extends StatelessWidget {
	  const RegisterPage({Key? key}) : super(key: key);

	  @override
	  Widget build(BuildContext context) {
	    return Scaffold(
	      backgroundColor: Colors.grey.shade50,
	      appBar: AppBar(
	        title: const Text("Crear Cuenta"),
	        backgroundColor: Colors.blue,
	        foregroundColor: Colors.white,
	        elevation: 0,
	        centerTitle: true,
	      ),
	      body: SafeArea(
	        child: SingleChildScrollView(
	          child: Padding(
	            padding: const EdgeInsets.all(24.0),
	            child: Column(
	              crossAxisAlignment: CrossAxisAlignment.start,
	              children: [
	                // Encabezado más atractivo
	                Center(
	                  child: Container(
	                    width: 80,
	                    height: 80,
	                    decoration: BoxDecoration(
	                      color: Colors.blue.shade50,
	                      borderRadius: BorderRadius.circular(20),
	                    ),
	                    child: Icon(
	                      Icons.person_add,
	                      size: 40,
	                      color: Colors.blue.shade600,
	                    ),
	                  ),
	                ),
	                const SizedBox(height: 24),
	                Center(
	                  child: Text(
	                    "Información Personal",
	                    style: TextStyle(
	                      fontSize: 24,
	                      fontWeight: FontWeight.bold,
	                      color: Colors.blue.shade800,
	                    ),
	                  ),
	                ),
	                const SizedBox(height: 8),
	                Center(
	                  child: Text(
	                    "Completa tus datos para registrarte",
	                    style: TextStyle(
	                      color: Colors.grey.shade600,
	                      fontSize: 16,
	                    ),
	                  ),
	                ),
	                const SizedBox(height: 32),
                
                // Formulario mejorado
                _buildRegisterField(
                  label: "Nombre completo",
                  icon: Icons.person_outline,
                  hint: "Ingresa tu nombre completo",
                ),
                const SizedBox(height: 20),
                _buildRegisterField(
                  label: "Correo electrónico",
                  icon: Icons.email_outlined,
                  hint: "nombre@ejemplo.com",
                  keyboardType: TextInputType.emailAddress,
                ),
                const SizedBox(height: 20),
                _buildRegisterField(
                  label: "Teléfono",
                  icon: Icons.phone_outlined,
                  hint: "Tu número de teléfono",
                  keyboardType: TextInputType.phone,
                ),
                const SizedBox(height: 20),
                _buildRegisterField(
                  label: "Contraseña",
                  icon: Icons.lock_outline,
                  hint: "Crea una contraseña segura",
                  isPassword: true,
                ),
                const SizedBox(height: 20),
                _buildRegisterField(
                  label: "Confirmar contraseña",
                  icon: Icons.lock_outline,
                  hint: "Repite la contraseña",
                  isPassword: true,
                ),
                const SizedBox(height: 36),
                
                // Botón de registro más atractivo
                SizedBox(
                  width: double.infinity,
                  height: 55,
                  child: ElevatedButton(
                    onPressed: () {
                      Navigator.pushReplacementNamed(context, "/main");
                    },
                    style: ElevatedButton.styleFrom(
                      shape: RoundedRectangleBorder(
                        borderRadius: BorderRadius.circular(14),
                      ),
                      backgroundColor: Colors.blue,
                      elevation: 3,
                      shadowColor: Colors.blue.shade200,
                    ),
                    child: const Text(
                      "Crear Cuenta",
                      style: TextStyle(
                        fontSize: 16,
                        fontWeight: FontWeight.w600,
                      ),
                    ),
                  ),
                ),
                const SizedBox(height: 20),
              ],
            ),
          ),
        ),
      ),
    );
  }

	  // Helper para campos de registro
	  Widget _buildRegisterField({
	    required String label,
	    required IconData icon,
	    required String hint,
	    bool isPassword = false,
	    TextInputType keyboardType = TextInputType.text,
	  }) {
	    return Column(
	      crossAxisAlignment: CrossAxisAlignment.start,
	      children: [
	        Padding(
	          padding: const EdgeInsets.only(left: 4, bottom: 8),
	          child: Text(
	            label,
	            style: TextStyle(
	              fontWeight: FontWeight.w600,
	              color: Colors.grey.shade800,
	            ),
	          ),
	        ),
	        TextField(
	          obscureText: isPassword,
	          keyboardType: keyboardType,
	          decoration: InputDecoration(
	            hintText: hint,
	            prefixIcon: Icon(icon, color: Colors.blue.shade400),
	            filled: true,
	            fillColor: Colors.white,
	            border: OutlineInputBorder(
	              borderRadius: BorderRadius.circular(14),
	              borderSide: BorderSide.none,
	            ),
	            enabledBorder: OutlineInputBorder(
	              borderRadius: BorderRadius.circular(14),
	              borderSide: BorderSide(color: Colors.grey.shade200),
	            ),
	            focusedBorder: OutlineInputBorder(
	              borderRadius: BorderRadius.circular(14),
	              borderSide: BorderSide(color: Colors.blue),
	            ),
	            contentPadding: const EdgeInsets.symmetric(vertical: 16),
	          ),
	        ),
	      ],
	    );
	  }
	}

	// Página de Calculadora - Rediseñada y solo visual
	class CalculatorPage extends StatelessWidget {
	  const CalculatorPage({Key? key}) : super(key: key);

	  @override
	  Widget build(BuildContext context) {
	    return Scaffold(
	      backgroundColor: Colors.grey.shade100,
	      appBar: AppBar(
	        title: const Text("Calculadora"),
	        backgroundColor: Colors.blue,
	        foregroundColor: Colors.white,
	        elevation: 0,
	        centerTitle: true,
	      ),
	      body: Column(
	        children: [
	          // Pantalla de la calculadora mejorada
	          Container(
	            width: double.infinity,
	            padding: const EdgeInsets.all(24.0),
	            decoration: BoxDecoration(
	              gradient: LinearGradient(
	                colors: [Colors.blue.shade600, Colors.blue.shade800],
	                begin: Alignment.topLeft,
	                end: Alignment.bottomRight,
	              ),
	              borderRadius: const BorderRadius.only(
	                bottomLeft: Radius.circular(30),
	                bottomRight: Radius.circular(30),
	              ),
	              boxShadow: [
	                BoxShadow(
	                  color: Colors.blue.shade300.withOpacity(0.5),
	                  blurRadius: 15,
	                  offset: const Offset(0, 5),
	                ),
	              ],
	            ),
	            child: Column(
	              crossAxisAlignment: CrossAxisAlignment.end,
	              children: [
	                const Text(
	                  "120 + 45",
	                  style: TextStyle(
	                    fontSize: 20.0,
	                    color: Colors.white70,
	                  ),
	                ),
	                const SizedBox(height: 8),
	                const Text(
	                  "165",
	                  style: TextStyle(
	                    fontSize: 48.0,
	                    fontWeight: FontWeight.bold,
	                    color: Colors.white,
	                  ),
	                ),
	                const SizedBox(height: 16),
	              ],
	            ),
	          ),
          
          // Teclado mejorado
          Expanded(
            child: Container(
              padding: const EdgeInsets.all(20.0),
              child: Column(
                children: [
                  Expanded(
                    child: Row(
                      children: [
                        _buildCalculatorButton("7"),
                        _buildCalculatorButton("8"),
                        _buildCalculatorButton("9"),
                        _buildCalculatorButton("÷", isOperator: true),
                      ],
                    ),
                  ),
                  Expanded(
                    child: Row(
                      children: [
                        _buildCalculatorButton("4"),
                        _buildCalculatorButton("5"),
                        _buildCalculatorButton("6"),
                        _buildCalculatorButton("×", isOperator: true),
                      ],
                    ),
                  ),
                  Expanded(
                    child: Row(
                      children: [
                        _buildCalculatorButton("1"),
                        _buildCalculatorButton("2"),
                        _buildCalculatorButton("3"),
                        _buildCalculatorButton("-", isOperator: true),
                      ],
                    ),
                  ),
                  Expanded(
                    child: Row(
                      children: [
                        _buildCalculatorButton("C", isFunction: true),
                        _buildCalculatorButton("0"),
                        _buildCalculatorButton("=", isEquals: true),
                        _buildCalculatorButton("+", isOperator: true),
                      ],
                    ),
                  ),
                ],
              ),
            ),
          ),
          
          // Botón volver más atractivo
          Padding(
            padding: const EdgeInsets.all(16.0),
            child: SizedBox(
              width: double.infinity,
              height: 55,
              child: ElevatedButton.icon(
                icon: const Icon(Icons.home_outlined),
                label: const Text("Volver al Menú Principal"),
                style: ElevatedButton.styleFrom(
                  backgroundColor: Colors.white,
                  foregroundColor: Colors.blue,
                  side: BorderSide(color: Colors.blue.shade300),
                  elevation: 0,
                  shape: RoundedRectangleBorder(
                    borderRadius: BorderRadius.circular(14),
                  ),
                ),
                onPressed: () {
                  Navigator.pushReplacementNamed(context, "/main");
                },
              ),
            ),
          ),
        ],
      ),
    );
	  }

	  // Helper para botones de calculadora
	  Widget _buildCalculatorButton(String text, {bool isOperator = false, bool isEquals = false, bool isFunction = false}) {
	    Color bgColor = Colors.white;
	    Color textColor = Colors.black87;
    
    if (isOperator) {
      bgColor = Colors.blue.shade100;
      textColor = Colors.blue.shade800;
    } else if (isEquals) {
      bgColor = Colors.green.shade100;
      textColor = Colors.green.shade800;
    } else if (isFunction) {
      bgColor = Colors.red.shade100;
      textColor = Colors.red.shade800;
    }
    
    return Expanded(
      child: Padding(
        padding: const EdgeInsets.all(6.0),
        child: Container(
          decoration: BoxDecoration(
            color: bgColor,
            borderRadius: BorderRadius.circular(16),
            boxShadow: [
              BoxShadow(
                color: Colors.grey.shade300,
                blurRadius: 3,
                offset: const Offset(0, 2),
              ),
            ],
          ),
          child: Center(
            child: Text(
              text,
              style: TextStyle(
                fontSize: 24.0,
                fontWeight: FontWeight.w600,
                color: textColor,
              ),
            ),
          ),
        ),
      ),
    );
	  }
	}

	// Clase para elementos FAQ
	class FAQItem {
	  final String question;
	  final String answer;
	  FAQItem({required this.question, required this.answer});
	}

	// Lista de 10 preguntas frecuentes concisas
	final List<FAQItem> faqList = [
	  FAQItem(
	    question: '¿Cómo puedo restablecer mi contraseña?',
	    answer: 'Haz clic en "¿Olvidaste tu contraseña?" en la pantalla de inicio de sesión y sigue las instrucciones enviadas a tu correo electrónico.',
	  ),
	  FAQItem(
	    question: '¿Cuáles son los métodos de pago aceptados?',
	    answer: 'Aceptamos tarjetas de crédito/débito, PayPal y transferencias bancarias. Todos los pagos están protegidos con encriptación de datos.',
	  ),
	  FAQItem(
	    question: '¿Cómo puedo actualizar mis datos personales?',
	    answer: 'Ve a la sección "Mi Perfil" y selecciona "Editar Información". Guarda los cambios después de actualizar tus datos.',
	  ),
	  FAQItem(
	    question: '¿La aplicación funciona sin internet?',
	    answer: 'No, nuestra aplicación requiere conexión a internet para acceder a tus datos y utilizar todas las funciones correctamente.',
	  ),
	  FAQItem(
	    question: '¿Cómo puedo contactar al soporte técnico?',
	    answer: 'Envía un correo a soporte@miapp.com o utiliza la opción "Contactar Soporte" en el menú de configuración.',
	  ),
	  FAQItem(
	    question: '¿Es segura mi información personal?',
	    answer: 'Sí, utilizamos encriptación de nivel bancario y nunca compartimos tus datos con terceros sin tu autorización previa.',
	  ),
	  FAQItem(
	    question: '¿Puedo usar la aplicación en múltiples dispositivos?',
	    answer: 'Sí, puedes iniciar sesión con tu cuenta en cualquier dispositivo compatible con iOS o Android.',
	  ),
	  FAQItem(
	    question: '¿Con qué frecuencia se actualiza la aplicación?',
	    answer: 'Lanzamos actualizaciones mensuales con mejoras y nuevas funciones. Las actualizaciones de seguridad se implementan de inmediato.',
	  ),
	  FAQItem(
	    question: '¿Cómo puedo cancelar mi suscripción?',
	    answer: 'Accede a "Configuración" → "Gestionar Suscripción" → "Cancelar". La cancelación será efectiva al final del período facturado.',
	  ),
	  FAQItem(
	    question: '¿La aplicación está disponible en otros idiomas?',
	    answer: 'Actualmente ofrecemos la aplicación en español, inglés, francés, alemán y portugués. Se pueden seleccionar en Configuración.',
	  ),
	];
