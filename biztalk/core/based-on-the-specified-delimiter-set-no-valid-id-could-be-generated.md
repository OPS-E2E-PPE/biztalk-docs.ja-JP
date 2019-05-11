---
title: 指定された区切り記号セットに基づいて、有効な ID を生成できませんでした。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ab5f018-b56f-4e3c-97e4-f9ea4258f6d9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5afc45bc15087cdc3867250e2f9c56e3cb4f8990
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358398"
---
# <a name="based-on-the-specified-delimiter-set-no-valid-id-could-be-generated"></a>指定された区切り記号セットに基づいて、有効な ID を生成できませんでした。
## <a name="details"></a>詳細  
  
|                 |                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------|
|  製品名   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]            |
| 製品バージョン |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                        |
|    イベント ID     |                                                    -                                                    |
|  イベント ソース   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI          |
|    コンポーネント    |                                               EDI エンジン                                                |
|  シンボル名  |                                                    -                                                    |
|  メッセージ テキスト   | 指定された区切り記号セットに基づいて有効な ID を生成できませんでした。 別の区切り記号セットを使用してください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、送信インターチェンジの識別子フィールドで使用されている文字が区切り記号と同じであったため、EDI 送信パイプラインで有効な ID 値を生成できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、メッセージを作成するために EDI 送信パイプラインで使用されている区切り記号の値を変更し、送信インターチェンジの識別子フィールドで使用されている文字と区切り記号が同じにならないようにします。 次のいずれかの操作を行います。  
  
-   解決済みのパーティに対して送信される X12 インターチェンジの場合、インターチェンジの受信者となるパーティの [ISA セグメントの定義] ページで区切り記号の設定を変更します。  
  
-   未解決のパーティに対して送信される X12 インターチェンジの場合、[ISA セグメントの定義] グローバル プロパティ ページで区切り記号の設定を変更します。  
  
-   解決済みのパーティに対して送信される EDIFACT インターチェンジの場合、インターチェンジの受信者となるパーティの [UNA セグメントの定義] ページで区切り記号の設定を変更します。  
  
-   未解決のパーティに対して送信される EDIFACT インターチェンジの場合、[UNA セグメントの定義] グローバル プロパティ ページで区切り記号の設定を変更します。