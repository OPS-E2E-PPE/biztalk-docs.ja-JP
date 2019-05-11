---
title: 指定された区切り記号セットに基づいて、有効な数字見つかりません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08887f7d-8256-4de3-8db9-b890451521ff
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63ad84e52fd66cb8430547ecd4e6a9e6dd054963
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358586"
---
# <a name="based-on-the-specified-delimiter-set-no-valid-digit-could-be-found"></a>指定された区切り記号セットに基づいて、有効な数字見つかりませんでした。
## <a name="details"></a>詳細  
  
|                 |                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------|
|  製品名   |           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]           |
| 製品バージョン |                       [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                       |
|    イベント ID     |                                                   -                                                    |
|  イベント ソース   |         [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI         |
|    コンポーネント    |                                               EDI エンジン                                               |
|  シンボル名  |                                                   -                                                    |
|  メッセージ テキスト   | 指定された区切り記号セットに基づいて有効な数字を見つけることができませんでした。 別の区切り記号セットを使用してください。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、送信インターチェンジのフィールドで使用されている数字が区切り記号と同じであるため、EDI 送信パイプラインが送信インターチェンジ生成時に有効な数字を見つけることができなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、EDI 送信パイプラインでメッセージを作成するために使用される区切り記号の値を変更し、送信インターチェンジのフィールドで使用されている数字が区切り記号と同じにならないようにします。 次のいずれかの操作を行います。  
  
-   解決済みのパーティに対して送信される X12 インターチェンジの場合、インターチェンジの受信者となるパーティの [ISA セグメントの定義] ページで区切り記号の設定を変更します。  
  
-   未解決のパーティに対して送信される X12 インターチェンジの場合、[ISA セグメントの定義] グローバル プロパティ ページで区切り記号の設定を変更します。  
  
-   解決済みのパーティに対して送信される EDIFACT インターチェンジの場合、インターチェンジの受信者となるパーティの [UNA セグメントの定義] ページで区切り記号の設定を変更します。  
  
-   未解決のパーティに対して送信される EDIFACT インターチェンジの場合、[UNA セグメントの定義] グローバル プロパティ ページで区切り記号の設定を変更します。