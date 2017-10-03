---
title: "アプリケーションを復元し、処理を有効にする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83144965-a51a-481a-afd6-7f573b69badb
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65ae913d45f45b13458294863714823a41ff4e44
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-restore-applications-and-enable-processing"></a>アプリケーションを復元し、処理を有効にする方法
BizTalk グループで、アプリケーションを構成し、次のトピックで説明した手順の後にアプリケーションの処理を有効にする[ランタイム コンピューターを更新する方法](../technical-guides/how-to-update-the-runtime-computers.md)です。  
  
### <a name="to-enable-application-configuration-and-restore-application-processing"></a>アプリケーションの構成を有効にして、アプリケーションの処理を復元するには  
  
1.  実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]グループ内の各 BizTalk サーバー上のアプリケーションのインストールの MSI ファイル。  
  
2.  実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を構成して、障害復旧サイトのアプリケーション グループ内の 1 つのサーバー上のアプリケーション構成の MSI ファイル。 名前は、受信場所と送信ポートは変わりません。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション構成の MSI ファイルがこれらの成果物が、障害回復環境で適切な場所を指すように、バインドを更新します。  
  
    > [!NOTE]  
    >  場合は受信場所と送信ポートには影響しません、実稼働サイトの損失、ある可能性がありますいないを災害復旧に固有の場所を使用してアプリケーションを再構成する必要です。  
  
3.  すべてのアプリケーションを有効にして復元アプリケーションの処理では、受信場所、ポート、およびホスト インスタンスを送信します。  
  
## <a name="see-also"></a>参照  
 [ランタイム コンピューターを回復します。](../technical-guides/recovering-the-runtime-computers.md)