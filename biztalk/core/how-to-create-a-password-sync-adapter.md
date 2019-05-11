---
title: パスワード同期アダプターを作成する方法 |Microsoft Docs
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
ms.openlocfilehash: a2c3ca305f86f541bd1cb681ed97aea7768e77c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65339930"
---
# <a name="how-to-create-a-password-sync-adapter"></a>パスワード同期アダプターを作成する方法
パスワード同期 (PS) アダプターは、通知からエンタープライズ シングル サインオン (SSO) を渡すためのパスワード同期ヘルパー コンポーネントを使用するアプリケーションです。 PS ヘルパー コンポーネントは、COM および .NET Framework インターフェイスを公開する、アダプターとは限りませんが COM コンポーネントであるに注意してください。 スタンドアロン プロセス、COM + アプリケーション、または Windows サービスとしてアダプターを設計することができます。  
  
### <a name="to-create-a-password-sync-adapter"></a>パスワード同期アダプターを作成するには  
  
1.  ご利用のプロバイダーは、active を使用して、エンタープライズ シングル サインオン サービス (ENTSSO) に通知`ISSOPSWrapper.InitializeAdapter`します。  
  
     `InitializeAdapter` 呼び出しを行っている同じプロバイダーは、通常、プロバイダーは、オンになって現在は、して、システムとのパスワードの更新を通信するために ENTSSO を通知します。 使用することも`InitializeAdapter`グループ アダプターなどの他のリソースをアクティブ化します。  
  
2.  使用してパスワードの更新を ENTSSO に送信`ISSOPSWrapper.SendNotification`します。  
  
     非 Windows システムからパスワードの更新を受け取る方法を決定する必要があります。 更新プログラムを受信した後は、ENTSSO を使用してログオン情報を渡すことができます`SendNotification`します。 なお`SendNotification`パスワードの更新を送信するだけではありません: アーキテクチャの`SendNotification`他の種類の通知を送信することもできます。  
  
3.  使用して ENTSSO からパスワードの更新を要求`ISSOPSWrapper.ReceiveNotification`します。  
  
     パスワード同期アダプターがプル テクノロジであるため、ENTSSO はアダプターを呼び出しません。 アダプターが定期的に呼び出す代わりに、`ReceiveNotification`パスワードの更新が使用できるかどうかを確認します。 WAIT フラグを設定することもできます`ReceiveNotification`します。 通知が利用可能になるまでスレッド待機ブロックを設定します。  
  
     ENTSSO がプレーン テキストでアダプターに、パスワードの変更を提供することに注意してください。 そのパスワードの情報が不正に漏えいを保護するアダプターの役目です。 スプーフィングから保護するアダプターの役割をもまたは、パスワード同期ヘルパー コンポーネントのスプーフィングを含む、他の無効なソースからの攻撃です。  
  
     使用して ENTSSO からパスワードの更新プログラムが表示されたら、`pReceiveNotification`パラメーター、非 Windows システムにこの情報を渡す必要があります。 同様`SendNotification`、リモート サーバーと通信する最善の方法を決定する必要があります。  
  
4.  アダプターを使用して、オフにする`ISSOPSWrapper.ShutdownAdapter`します。  
  
     `ShutdownApplication` 必要があります、最後のメソッドは、アダプターによって呼び出され、アダプターが送信されなく、ENTSSO にパスワードの更新が表示されるかを示します。  
  
     ENTSSO にアダプターがシャット ダウン中に、最大バッファー サイズの制限をユーザーが、パスワード変更がバッファーすることに注意してください。  
  
## <a name="see-also"></a>参照  
 [エンタープライズ シングル サインオンを使用したプログラミング](../core/programming-with-enterprise-single-sign-on.md)   
 [パスワードの同期](../core/synchronizing-passwords.md)