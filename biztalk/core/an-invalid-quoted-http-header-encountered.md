---
title: 無効な HTTP ヘッダーが検出されました引用符で囲まれた |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb530ee6-ec6a-4791-ae99-b9db426c0896
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff1372dc2eea57843d6d671e617aeeb2b8e90dea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359339"
---
# <a name="an-invalid-quoted-http-header-encountered"></a>発生した無効な引用符で囲まれた HTTP ヘッダー
## <a name="details"></a>詳細  
  
|                 |                                                                                                              |
|-----------------|--------------------------------------------------------------------------------------------------------------|
|  製品名   |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| 製品バージョン |                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                          |
|    イベント ID     |                                                      -                                                       |
|  イベント ソース   |            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI            |
|    コンポーネント    |                                                  AS2 エンジン                                                  |
|  シンボル名  |                                                      -                                                       |
|  メッセージ テキスト   | 無効な引用符で囲まれた HTTP ヘッダーが発生しました。  詳細は次のとおりです。ヘッダー名:"{0}"ヘッダーの値:"{1}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2 受信パイプラインまたはため、AS2 送信パイプラインが AS2 メッセージを処理できなかったことを示します、AS2 の名前からまたは AS2 のメッセージのメッセージを HTTP ヘッダーが正しく示されていません。 ヘッダー名は、スペース、円記号、または二重引用符で囲んだ名前に対応するために引用符で囲まれました。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、規則に従って、AS2 メッセージのヘッダー名を引用符に記載されている RFC 4130 のセクション 6.2「AS2 System Identifiers」"MIME ベース セキュリティで保護されたピア ツー ピア Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"。