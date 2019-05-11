---
title: 受信確認 (Mdn) (AS2) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb2bf98a-deb4-460f-a1fc-3d2397c39470
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81d1eb8c500ac746606da82509fb74e4d9afeb6a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391383"
---
# <a name="configuring-acknowledgements-mdns-as2"></a>受信確認 (Mdn) (AS2) の構成
パートナー アグリーメントでは、AS2 メッセージを受信するパーティの MDN 応答を生成および返送を指定できます。  
  
> [!IMPORTANT]
>  オフにした場合、このページで、次のプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。  
> 
> - **MDN を受信しない場合は AS2 メッセージ再送信** チェック ボックスと関連プロパティ  
>   -   **送信ポートの設定を上書き** チェック ボックスと関連プロパティ  
> 
>   プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-acknowledgements"></a>受信確認を構成するには  
  
1. AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2. 一方向アグリーメント タブで、次のようにクリックします。**受信確認 (Mdn)** します。  
  
3. 選択、 **MessageBox にルーティング/配信の受信 MDN を処理する**をパススルー メッセージとしてし、メッセージ ボックスに、A2 デコーダ経由の MDN をルーティングする チェック ボックス。 このプロパティを選択すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]昇格、`IsAS2MdnResponseMessage`ルーティングを行うのためのプロパティ。  
  
4. オンにした場合、**検証と MSDN のメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティ、**検証**] ページで、[、 **mdn を要求する**チェック ボックスをオンの場合、取引先は、AS2 メッセージへの応答で MDN を生成する必要があります。  
  
    場合、 **mdn を要求する** チェック ボックスが選択されている次のプロパティを設定することもできます場合、。  
  
   1. 選択、**署名付き MDN を要求** チェック ボックスとの間、**署名アルゴリズム**ドロップダウン選択 MIC アルゴリズム取引先が MDN に署名するために使用する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] MD5、SHA1、SHA2 をサポート (SHA256 (既定値)、SHA384、SHA512)。
    
      > [!NOTE]
      > **以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]以降のバージョン**、SHA2 サポートが自動的に含まれます。 以前[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]バージョンを参照してください[KB 3123748](https://support.microsoft.com/kb/3123748)します。
  
   2. 選択、**非同期 MDN を要求する**チェック ボックスをオンし、 **- Receipt-delivery-option (URL)** テキスト ボックスに、受信側パーティは MDN を送信する必要がある URL を入力します。  
  
       場合、**非同期 MDN を要求する** チェック ボックスが選択されている次のプロパティを設定することもできます場合、。  
  
      1. 選択、 **MDN を受信しない場合は再送信 AS2 メッセージ**AS2 メッセージの再送信を有効にする チェック ボックス。 値を入力**最小 AS2 メッセージ再送信間隔**、**数の AS2 メッセージ再送信試行**と**AS2 メッセージ再**を指定するフィールド、間隔、最大試行回数と、メッセージの再送信を停止するタイミングを再試行してください。  
  
         > [!NOTE]
         >  選択する必要があります、**レポートを有効にする**チェック ボックスをオン、**全般プロパティ**のページ、**全般**タブを選択する前に**再送信 AS2 メッセージの場合は MDN されません受信した**します。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] AS2 レポートを AS2 メッセージ再送信するタイミングを決定するために保存された追跡情報を使用します。  
  
      2. 場合**MDN を受信しない場合は再送信 AS2 メッセージ** チェック ボックスを選択すると、確認**送信ポートの設定を上書き**を指定する、 **HTTP 最小再試行間隔**と**HTTP 再試行の回数**します。 値を入力、 **HTTP しようとすると停止の後で再試行**を HTTP アダプターを使用した再試行の最大時間を指定するフィールド。  
  
   3. 選択した場合、**非同期 MDN を要求する** チェック ボックスの URL を指定して **- Receipt-delivery-option (URL)** プロパティ、**ディス ポジション-通知-に**テキストボックスで、既定では、同じ URL に設定します。 選択しなかった場合、**非同期 MDN を要求する** チェック ボックスの値を入力する必要があります**ディス ポジション-通知-に**します。 このフィールドの値は、AS2 処理時には使用されません。  
  
5. をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [AS2 アグリーメントのプロパティの構成](../core/configuring-as2-agreement-properties.md)