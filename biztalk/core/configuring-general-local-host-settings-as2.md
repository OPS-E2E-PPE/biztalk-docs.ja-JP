---
title: 全般的なローカル ホスト設定 (AS2) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 980daac2-8387-44cc-ae55-38639f759668
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b990a44c9599ff725bdd19f7bfdd8286ec11487d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391111"
---
# <a name="configuring-general-local-host-settings-as2"></a>全般的なローカル ホスト設定の構成 (AS2)
ローカル ホストの全般設定の一部として、AS2 メッセージとメッセージの AS2 ヘッダーの一部として、ファイル名を保持するかどうかのコンテンツの種類を指定できます。  
  
> [!IMPORTANT]
>  オフにした場合、このページで、すべてのプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。  
>   
>  プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-the-general-settings"></a>[全般] 設定を構成するには  
  
1.  AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**ローカル ホスト設定**セクションで、**全般**します。  
  
3.  選択、**証明書失効リストの確認メッセージを送信する前に**送信メッセージの署名に使用される証明書を証明書失効リストに含まれているかどうかを判断する チェック ボックスを示すその it が失効、または有効期限の日付が渡されるかどうか。 そうである場合、BizTalk Server は、メッセージ暗号化は行われませんが、中断します。 このプロパティをオフにした場合、この確認は行われません。  
  
    > [!NOTE]
    >  証明書失効リストを取得および検索する場合には遅延が生じます。  
  
4.  **既定のコンテンツの種類**、送信 AS2 メッセージのパーティを使用する必要がある既定のコンテンツ タイプを選択します。 場合、`ContentType`プロパティをこの値の設定が送信メッセージの生成に使用されます。 それ以外であること、メッセージのボディ部のコンテキストにおける設定**既定のコンテンツの種類**プロパティを使用します。  
  
5.  選択、 **MIME ヘッダーでファイル名を送信**送信 AS2 メッセージの MIME ヘッダーの一部としてファイル名を送信する チェック ボックス。 ファイル名を指定するには、次のように選択します。**ファイル名の指定**または**システム ファイル名を生成**します。  
  
    > [!NOTE]
    >  選択**システム ファイル名を生成**AS2 メッセージで送信される各添付ファイルのファイル名として新しい GUID 値が生成されます。  
  
6.  選択した場合**ファイル名の指定**、内の文字列値またはコンテキスト プロパティを入力、**ファイル名の指定**フィールド。 有効にすることも**場合メッセージは中断コンテキスト プロパティ (%property% など)見つかりません。** 選択されているコンテキスト プロパティは、送信メッセージが存在しない場合、メッセージを中断します。  
  
    > [!NOTE]
    >  コンテキスト プロパティを指定するには、プロパティ名に % 文字で囲みます。 たとえば、`%FILE.ReceivedFileName%` のようにします。  
  
7.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [ローカル ホスト設定の構成 (AS2)](../core/configuring-local-host-settings-as2.md)