---
title: 無効な繰り返し回数があるため、コンポーネントを繰り返すことはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 040d7ea4-60a9-495f-91d7-b5b868957e2d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9bb4cd603084a4bd105423a556d6480051fc0a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391661"
---
# <a name="component-cannot-repeat-because-it-has-an-invalid-repetition-count"></a>無効な繰り返し回数があるため、コンポーネントを繰り返すことはできません。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                            SchemaCode118EInvalidRepetition                             |
|  メッセージ テキスト   |           無効な繰り返し数があるコンポーネントを繰り返すことはできません。 {0}           |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、スキーマで繰り返しが許可されていないにもかかわらず、インターチェンジで要素コンポーネント、要素、セグメント、またはループが繰り返されていたため、受信パイプラインで受信インターチェンジを処理できなかったか、送信パイプラインで送信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジに要素コンポーネント、要素、セグメント、またはループの繰り返しがなく、スキーマの要件どおりであることを確認し、メッセージを再送信します。