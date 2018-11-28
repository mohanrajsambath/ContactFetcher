# ContactFetcher
An app to read all contacts with emails and mobile numbers. It also supports multiple emails and mobile numbers.

**Current version:** [ ![Download](https://api.bintray.com/packages/raghavsatyadev/Maven/ContactFetcher/images/download.svg?version=0.1.0) ](https://bintray.com/raghavsatyadev/Maven/ContactFetcher/0.1.0/link)

# Setup
To use this library your minSdkVersion must be >= 16.

In the build.gradle of your project add:

```gradle
repositories {
    maven {
        url  "https://dl.bintray.com/raghavsatyadev/Maven" 
    }
}
```

In the build.gradle of your app module add:

```gradle
dependencies {
    compile 'com.rocky.contactfetcher:contactfetcher:0.1.0'
}
```

# Example

```java
ContactFetcher.getContacts(this, new ContactListener<Contact>() {
      @Override
      public void onNext(Contact contact) {
          adapter.addItem(contact);
      }

      @Override
      public void onError(Throwable error) {
          Log.e(TAG, "onError: ", error);
      }

      @Override
      public void onComplete() {

      }
  });
```

in onRequestPermissionsResult() method

```java
@Override
public void onRequestPermissionsResult(int requestCode, @NonNull String[] permissions,
                                       @NonNull int[] grantResults) {
    ContactFetcher.resolvePermissionResult(this, requestCode, permissions, grantResults);
}
```

This library is highly inspired by **RXContacts :**  https://github.com/UlrichRaab/rx-contacts