---
title: (R2) のインターチェンジから区切り記号セットを読み取ることができませんでした。Microsoft Docs
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
ms.openlocfilehash: 7208e9be2d8c5f28420151af060720f72eaa1913
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390222"
---
# <a name="delimiter-set-could-not-be-read-from-the-interchange-r2"></a>(R2) のインターチェンジから区切り記号セットを読み取ることができませんでした。
## <a name="details"></a>詳細  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| 製品バージョン |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                 |
|    イベント ID     |                                                             -                                                             |
|  イベント ソース   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                   |
|    コンポーネント    |                                                        EDI エンジン                                                         |
|  シンボル名  |                                                             -                                                             |
|  メッセージ テキスト   | インターチェンジから区切り記号セットを読み取ることができませんでした。 属性 DelimiterSetSerializedData がルート ノードにありません。 |

## <a name="explanation"></a>説明  
 このエラーは、インターチェンジに区切り記号セットの値が含まれていないことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  

- 次のように、インターチェンジに区切り記号セットの値を追加します。  

  1.  メッセージを開きます。  

  2.  インターチェンジの UNA セグメントがあるかどうかを決定します。 UNA セグメントがない場合は、インターチェンジに UNA セグメントを追加するパートナーに問い合わせてください。  

- よう、EfactDelimiters パイプライン プロパティの区切り記号の値を入力します。  

  1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、受信場所を右クリックするか送信ポートのプロパティを設定するパイプラインを使用します。 **[プロパティ]** をクリックします。  

  2. プロパティを設定する対象のパイプラインの横にある省略記号ボタン ([…]) をクリックします。  

  3. (UNA1、UNA2、UNA3、UNA4、UNA5、および UNA6) のコンマ区切りのリストとして UNA 区切り記号の値を入力として必要な既定値を変更します。 既定値は次のとおりです。0x3A、0x2B、0x2C、0x3F、0x20、0x27 します。  

  4. **[OK]** をクリックします。
