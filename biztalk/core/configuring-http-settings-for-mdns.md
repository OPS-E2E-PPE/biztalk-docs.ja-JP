---
title: Mdn の HTTP 設定の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5c877e85-7887-43a9-9fd4-0853b573213f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40496efd556d30f87f33d647ab97edb123453c5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355418"
---
# <a name="configuring-http-settings-for-mdns"></a>Mdn の HTTP 設定を構成します。
MDN 関連の HTTP 設定の一部として、Mdn を受信する Web サーバーで想定されているプロパティを指定できます。  
  
> [!IMPORTANT]
>  オフにした場合、このページで、すべてのプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。  
>   
>  プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-mdn-related-http-settings"></a>MDN 関連の HTTP 設定を構成するには  
  
1.  AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**ローカル ホスト設定**セクションで、 **Mdn の HTTP 設定**します。  
  
3.  選択、**を無視する SSL 証明書名の不一致**サーバー名が SSL 証明書が生成されたサーバー名が一致しない場合、SSL 接続は引き続きことを確認する チェック ボックスが受け入れられます。  
  
4.  クリックして**HTTP expect: 100-continue** HTTP Expect ヘッダーを 100 に設定する-続行すると、ポストされたデータは、最初の HTTP 要求がコンテンツを要求するサーバーの間、待機に含まれないことを指定します。  
  
5.  クリックして**保持の HTTP 接続をアライブ**要求と応答のサイクルが完了した後、HTTP 接続がアライブする保持を要求します。  
  
6.  クリックして**HTTP のヘッダー**を 1 行に、HTTP content-type ヘッダーをオンにします。  
  
7.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [ローカル ホスト設定の構成 (AS2)](../core/configuring-local-host-settings-as2.md)