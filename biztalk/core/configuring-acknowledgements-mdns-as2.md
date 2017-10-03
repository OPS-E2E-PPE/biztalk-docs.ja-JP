---
title: "受信確認 (Mdn) (AS2) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb2bf98a-deb4-460f-a1fc-3d2397c39470
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2df8c92d37d5f6bc8fbf8d6d77fb698e6178036
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-acknowledgements-mdns-as2"></a>受信確認 (MDN) の構成 (AS2)
パートナー アグリーメントで、AS2 メッセージを受信するパーティの MDN 応答の生成方法と返送方法を指定できます。  
  
> [!IMPORTANT]
>  オフにした場合、このページで、次のプロパティが無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
>   
>  -   **MDN を受信しない場合、AS2 メッセージを再送** チェック ボックスと関連プロパティ  
> -   **送信ポートの設定を上書き** チェック ボックスと関連プロパティ  
>   
>  プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-acknowledgements"></a>受信確認を構成するには  
  
1.  AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブで、をクリックして**受信確認 (Mdn)**です。  
  
3.  選択、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**をパススルー メッセージとしてし、さらに、メッセージ ボックスには、A2 デコーダ経由 MDN をルーティングする チェック ボックスです。 このプロパティを選択すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] により `IsAS2MdnResponseMessage` プロパティがルーティング用に昇格されます。  
  
4.  オンにした場合、**メッセージ ヘッダーの代わりに、検証と MSDN のアグリーメントの設定を使用して**プロパティに、**検証**] ページで、[、 **mdn を要求する**チェック ボックスをオンの場合、取引先は、AS2 メッセージへの応答で MDN を生成する必要があります。  
  
     場合、 **mdn を要求する** チェック ボックスが選択されている次のプロパティを設定することもできます場合、。  
  
    1.  選択、**署名付き MDN を要求** チェック ボックスとの間、**署名アルゴリズム**ドロップダウン選択 MIC アルゴリズム取引先が MDN に署名するために使用する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]MD5、SHA1、SHA2 をサポートしています (SHA256 (既定)、SHA384、および sha512 が使用)。
    
        > [!NOTE] 
        > **以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]以降のバージョン**、SHA2 サポート自動的に含まれています。 以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョンを参照してください[KB 3123748](https://support.microsoft.com/kb/3123748)です。
  
    2.  選択、**非同期 MDN を要求する**チェック ボックスをオンし、 **- Receipt-delivery-option (URL)**テキスト ボックスで、受信側パーティは MDN を送信する必要がありますの URL を入力します。  
  
         場合、**非同期 MDN を要求する** チェック ボックスが選択されている次のプロパティを設定することもできます場合、。  
  
        1.  選択、 **MDN を受信しない場合は再送信 AS2 メッセージ**AS2 メッセージの再転送を有効にする チェック ボックスです。 値を入力**最小 AS2 メッセージ再送信間隔**、**数の AS2 メッセージ再送信試行**と**AS2 メッセージ再送信中止**を指定するフィールド、間隔、最大試行回数と、メッセージの再送信を停止するタイミングを再試行してください。  
  
            > [!NOTE]
            >  選択する必要があります、**レポートをオンに**チェック ボックスをオン、**全般プロパティ**のページ、**全般** タブを選択する前に**再送信 AS2 メッセージの場合は MDN されません受信した**です。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、AS2 レポートに保存された追跡情報を使用して、AS2 メッセージを再送信するタイミングを決定します。  
  
        2.  場合**MDN を受信しない場合は再送信 AS2 メッセージ** チェック ボックスを選択すると、確認**送信ポートの設定を上書き**を指定する、 **HTTP 最小再試行間隔**と**HTTP 再試行回数**です。 値を入力して、 **HTTP しようとすると停止の後に再試行**を HTTP アダプターを使用した再試行の最大時間を指定するフィールドです。  
  
    3.  選択した場合、**非同期 MDN を要求する** チェック ボックスの URL を指定して**- Receipt-delivery-option (URL)** 、プロパティ、**廃棄で通知を**テキストボックスで、既定では、同じ URL に設定します。 選択しなかった場合、**非同期 MDN を要求する** チェック ボックスの値を入力する必要があります**廃棄する**です。 このフィールドの値は、AS2 処理時には使用されません。  
  
5.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [AS2 アグリーメント プロパティの構成](../core/configuring-as2-agreement-properties.md)