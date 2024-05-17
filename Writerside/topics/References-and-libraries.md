# References and libraries

extract from `build.gradle.kts` :
```Kotlin
    dependencies {


    implementation(libs.androidx.core.ktx)
    implementation(libs.androidx.lifecycle.runtime.ktx)
    implementation(libs.androidx.activity.compose)
    implementation(platform(libs.androidx.compose.bom))
    implementation(libs.androidx.ui)
    implementation(libs.androidx.ui.graphics)
    implementation(libs.androidx.ui.tooling.preview)
    implementation(libs.androidx.material3)
    implementation(libs.androidx.lifecycle.runtime.compose)

    // Room
    implementation(libs.androidx.room.runtime)
    implementation(libs.androidx.navigation.compose)
    annotationProcessor(libs.androidx.room.compiler)
    ksp(libs.androidx.room.compiler)
    implementation(libs.androidx.room.ktx)

//    implementation(libs.ktor.client.core)
//
//    // Moteur populaire
//    implementation(libs.ktor.client.cio)
//
//    // Exemples de plugins
//    implementation(libs.ktor.serialization.kotlinx.json)
//    implementation(libs.ktor.client.content.negotiation)
//    implementation(libs.ktor.client.logging)

    // Coil
    implementation(libs.coil.compose)

    // AppolloGraphQL
    implementation(libs.apollo.runtime)

    // Cookie Jar
    implementation (libs.okhttp.urlconnection)

    // CameraX
    implementation(libs.androidx.camera.camera2)
    implementation(libs.androidx.camera.lifecycle)
    implementation(libs.androidx.camera.view)
    implementation(libs.androidx.camera.extensions)

    // Accompanist

    implementation(libs.accompanist.permissions)

    //file picker
    implementation(libs.mpfilepicker)

    //pdf viewer
    implementation(libs.bouquet)


    testImplementation(libs.junit)
    androidTestImplementation(libs.androidx.junit)
    androidTestImplementation(libs.androidx.espresso.core)
    androidTestImplementation(platform(libs.androidx.compose.bom))
    androidTestImplementation(libs.androidx.ui.test.junit4)
    debugImplementation(libs.androidx.ui.tooling)
    debugImplementation(libs.androidx.ui.test.manifest)

}

apollo{
    service("moneyminder") {
        packageName.set("com.example")
        mapScalar("Decimal","kotlin.Float", "com.apollographql.apollo3.api.FloatAdapter")
    }
```

A Short description on third party libraries used for this project :

Interaction with graphQL : <a href="https://www.apollographql.com/docs/">`Apollo 3`</a>

web client : <a href="https://square.github.io/okhttp/">`okhttp`</a> - thanks to `ngocchung` for the example about using okhttp with multipart body and functions.

web images : <a href="https://github.com/coil-kt/coil">`coil`</a>

Camera : Huge thanks to `Yenneck Reiss`, on what the camera component is very based on their <a href="https://github.com/YanneckReiss/JetpackComposeCameraXShowcase?tab=readme-ov-file"> repository </a>

OS file picking : using `compose-multiplatform-file-picker" from <a href="https://github.com/Wavesonics/compose-multiplatform-file-picker"> this </a> repository

pdf viewer : Thanks to `GRizzi91` for the <a href="https://github.com/GRizzi91/bouquet">`bouquet`</a> library, very easy to use for showing pdfs and offering multiple choices to display them on jetpack compose.

Everything else is from `android`, check the <a href="https://developer.android.com/reference/kotlin/androidx/compose/runtime/package-summary"> reference or documentation </a> for more info.