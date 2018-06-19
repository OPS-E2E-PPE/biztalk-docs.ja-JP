---
title: パスワード同期アダプターを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caa5bd13-efd9-4544-b5df-17d01c6ac5d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c47381cc1ed71788673602c1db7eec5b5ac049ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249370"
---
# <a name="how-to-create-a-password-sync-adapter"></a>パスワード同期アダプターを作成する方法
PS (パスワード同期) アダプターは、パスワード同期ヘルパー コンポーネントを使用して、エンタープライズ シングル サインオン (SSO) との間で通知を渡したり、受け取ったりするアプリケーションです。 PS ヘルパー コンポーネントは、COM および .NET フレームワーク インターフェイスを公開しますが、アダプターが COM コンポーネントである必要はありません。 アダプターは、スタンドアロン プロセス、COM+ アプリケーション、または Windows サービスとしてデザインできます。  
  
### <a name="to-create-a-password-sync-adapter"></a>パスワード同期アダプターを作成するには  
  
1.  `ISSOPSWrapper.InitializeAdapter` を使用して、ENTSSO (エンタープライズ シングル サインオン) サービスに、プロバイダーがアクティブであることを通知します。  
  
     `InitializeAdapter` は、プロバイダー (通常は呼び出しを実行するプロバイダーと同じ) が現在オンになっていて、システムのパスワードの更新のやり取りが可能であることを ENTSSO に通知します。 また、`InitializeAdapter` を使用して、グループ アダプターなど、他のリソースをアクティブ化することもできます。  
  
2.  `ISSOPSWrapper.SendNotification` を使用して、パスワードの更新を ENTSSO に送信します。  
  
     Windows 以外のシステムからパスワードの更新を受け取る方法を決定する必要があります。 更新を受け取った後で、`SendNotification` を使用してその情報を ENTSSO に渡すことができます。 なお`SendNotification`パスワードの更新を送信するだけではありません: のアーキテクチャ`SendNotification`他の種類の通知を送信することもできます。  
  
3.  `ISSOPSWrapper.ReceiveNotification` を使用して、ENTSSO からのパスワードの更新を要求します。  
  
     パスワード同期アダプターはプル テクノロジであるため、ENTSSO はアダプターを呼び出しません。 代わりに、アダプターは定期的に `ReceiveNotification` を呼び出して、パスワードの更新が利用可能であるかを確認します。 WAIT フラグを `ReceiveNotification` に設定することもできます。 WAIT を設定すると、通知が利用可能になるまでスレッドをブロックします。  
  
     ENTSSO がパスワードの変更をプレーン テキストでアダプターに配信することに注意してください。 パスワード情報が不正に漏えいされないように保護するのはアダプターの役割です。 また、他の無効なソースからの偽装や攻撃 (パスワード同期ヘルパー コンポーネントの偽装など) からアダプター自身を保護することもアダプターの役割です。  
  
     `pReceiveNotification` パラメーターを使用して ENTSSO からパスワードの更新を受け取った後で、この情報を Windows 以外のシステムに渡す必要があります。 `SendNotification` の場合と同じように、リモート サーバーと通信する最良の方法を決定する必要があります。  
  
4.  `ISSOPSWrapper.ShutdownAdapter` を使用してアダプターをオフにします。  
  
     `ShutdownApplication` は、アダプターによって呼び出される最後のメソッドであり、アダプターが ENTSSO とのパスワードの更新のやり取りをそれ以上行わないことを示します。  
  
     アダプターがシャットダウンしている間、ENTSSO は、すべてのパスワードの変更をバッファー サイズいっぱいになるまで書き込みます。  
  
## <a name="see-also"></a>参照  
 [エンタープライズ シングル サインオンを使用したプログラミング](../core/programming-with-enterprise-single-sign-on.md)   
 [パスワードの同期](../core/synchronizing-passwords.md)