---
title: 区切り記号セットは、インターチェンジ (R2) から読み取れませんでした |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17bdd32e-d43f-4f59-af27-5d3054fd5432
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3836b218ac3596bef25edb29eaf72c38f65b6e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239082"
---
# <a name="delimiter-set-could-not-be-read-from-the-interchange-r2"></a>インターチェンジから区切り記号セットを読み込めませんでした (R2)
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|インターチェンジから区切り記号セットを読み込めませんでした。 ルート ノードに属性 DelimiterSetSerializedData が見つかりません。|  
  
## <a name="explanation"></a>説明  
 このエラーは、インターチェンジに区切り記号セット値が含まれていないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   次のようにしてインターチェンジに区切り記号セットの値を追加します。  
  
    1.  メッセージを開きます。  
  
    2.  インターチェンジに UNA セグメントが含まれているかどうかを確認します。 UNA セグメントがない場合は、インターチェンジへの UNA セグメントの追加をパートナーに依頼します。  
  
-   次のようにして EfactDelimiters パイプライン プロパティに区切り記号の値を入力します。  
  
    1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、プロパティを設定するパイプラインを使用している受信場所または送信ポートを右クリックします。 **[プロパティ]** をクリックします。  
  
    2.  プロパティを設定する対象のパイプラインの横にある省略記号ボタン ([…]) をクリックします。  
  
    3.  コンマで区切ったリストとして UNA 区切り記号の値を入力し (UNA1、UNA2、UNA3、UNA4、UNA5、および UNA6 用)、必要に応じて既定値を変更します。 既定値は次のとおり: 0x3A、0x2B、0x2C、0x3F、0x20、0x27 です。  
  
    4.  **[OK]** をクリックします。