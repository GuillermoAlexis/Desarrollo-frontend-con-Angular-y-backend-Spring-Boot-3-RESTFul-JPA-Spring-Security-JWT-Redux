# 🚀 Introducción a Angular + TypeScript

Angular es un **framework de JavaScript** (basado en **TypeScript**) creado por Google para construir **aplicaciones web modernas, responsivas y escalables**.  
Se utiliza ampliamente para desarrollar **Single Page Applications (SPA)** con experiencia de usuario fluida.

**TypeScript** es el **lenguaje principal en Angular**: añade tipado estático, clases, interfaces, genéricos y decoradores, mejorando productividad y mantenibilidad.

---

## 🟦 Lenguaje de Programación: TypeScript

- Es un **superconjunto de JavaScript (ECMAScript)**.  
- **Clases e interfaces** para organizar el código.  
- **Tipado fuerte** (estático u opcional).  
- **Constructores, métodos y atributos**.  
- Soporte de **Generics** para reutilización segura.  
- Uso de **decoradores** (muy utilizados en Angular: `@Component`, `@Injectable`, etc.).  

---

## 🟩 Framework: Angular

### ✨ Características principales
- **Aplicaciones web responsivas** (desktop, tablet, móvil).  
- **SPA (Single Page Application)** con navegación fluida.  
- **RxJS** para flujos de datos **reactivos**.  
- **Asíncrono**: comunicación en segundo plano con servidores.  
- **Modular y escalable**: basado en componentes y módulos reutilizables.  

### 🧩 Conceptos clave
- **Componentes** → Encapsulan vista, lógica y estilos.  
- **Directivas** → Modifican el comportamiento de elementos HTML.  
- **Pipes** → Transforman datos en las vistas (ej: fecha, moneda, mayúsculas).  
- **Servicios (Services)** → Centralizan lógica de negocio y comunicación con backend.  
- **Routing** → Sistema de navegación y manejo de parámetros en URL.  
- **Formularios (Template-driven & Reactive Forms)** → Captura y validación de datos.  
- **HTTPClient** → Consumo de APIs RESTful (GET, POST, PUT, DELETE).  
- **Observables (RxJS)** → Modelo reactivo para datos asíncronos.  
- **Interceptors** → Añadir cabeceras (JWT) o manejar errores globales.  

---

# 🛠️ Guía rápida: primer proyecto Angular

## 2️⃣ Instala Angular CLI
```
npm install -g @angular/cli
ng version
```

---

## 3️⃣ Crea un proyecto
```
ng new mi-app
# ? Add routing? Yes
# ? Stylesheet format? SCSS (o tu preferido)
cd mi-app
```

---

## 4️⃣ Inicia el servidor
```
ng serve -o
# Abre: http://localhost:4200
```

---

## 5️⃣ Estructura mínima
```
mi-app/
 ├─ src/
 │  ├─ app/
 │  │  ├─ core/        # servicios globales, interceptores
 │  │  ├─ shared/      # componentes/pipes reutilizables
 │  │  ├─ pages/       # páginas/feature modules
 │  │  ├─ app-routing.module.ts
 │  │  └─ app.module.ts
 │  ├─ assets/
 │  └─ environments/   # variables por ambiente
 └─ angular.json
```

---

## 6️⃣ Generadores útiles
```
ng generate component pages/home
ng generate service core/api
ng generate module pages/products --route products --module app.module
```

---

## 7️⃣ Consumir una API (ejemplo básico)

**api.service.ts**
```ts
@Injectable({ providedIn: 'root' })
export class ApiService {
  private baseUrl = 'http://localhost:8080/api';
  constructor(private http: HttpClient) {}

  getProducts(): Observable<Product[]> {
    return this.http.get<Product[]>(`${this.baseUrl}/products`);
  }
}
```

**products.component.ts**
```ts
@Component({ selector: 'app-products', templateUrl: './products.component.html' })
export class ProductsComponent implements OnInit {
  products: Product[] = [];
  constructor(private api: ApiService) {}
  ngOnInit() { this.api.getProducts().subscribe(res => this.products = res); }
}
```

---

## 8️⃣ Interceptor de autenticación (JWT)
```ts
@Injectable()
export class AuthInterceptor implements HttpInterceptor {
  intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
    const token = localStorage.getItem('token');
    const authReq = token ? req.clone({ setHeaders: { Authorization: `Bearer ${token}` } }) : req;
    return next.handle(authReq);
  }
}
```

---

## 9️⃣ Environments
```ts
// environment.ts
export const environment = { production: false, apiUrl: 'http://localhost:8080/api' };
```

---

## 🔟 Formularios reactivos
```ts
form = this.fb.group({
  email: ['', [Validators.required, Validators.email]],
  password: ['', [Validators.required, Validators.minLength(6)]],
});
```

---

## 1️⃣1️⃣ Routing básico
```ts
const routes: Routes = [
  { path: 'login', component: LoginComponent },
  { path: 'products', component: ProductsComponent },
  { path: '', redirectTo: 'products', pathMatch: 'full' }
];
```

---

## 1️⃣2️⃣ Build producción
```
ng build --configuration production
# salida en: dist/mi-app
```

---

# 🧩 Plugins recomendados (Visual Studio Code)

Para mejorar la experiencia de desarrollo con Angular + TypeScript:

- **Angular Language Service** → Autocompletado y diagnóstico en plantillas Angular.  
- **Angular Snippets (John Papa)** → Atajos de código para Angular.  
- **Auto Close Tag** → Cierre automático de etiquetas HTML/XML.  
- **Auto Rename Tag** → Renombrado automático de etiquetas en pareja.  
- **Material Icon Theme** → Iconos de Material Design para reconocer fácilmente archivos y carpetas.  

---

# 📚 Recursos útiles

- [📘 Angular Docs](https://angular.io/docs)  
- [🚀 Guía de inicio rápido](https://angular.io/start)  
- [🟦 TypeScript Docs](https://www.typescriptlang.org/docs/)  
- [⚡ RxJS](https://rxjs.dev/)  
