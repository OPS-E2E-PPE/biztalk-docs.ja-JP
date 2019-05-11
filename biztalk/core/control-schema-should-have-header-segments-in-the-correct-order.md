---
title: コントロールのスキーマが正しい順序でのヘッダー セグメントが必要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88f38e8f-243a-467f-84bd-a232ef148b4b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fee939bb14b98dc66373d754af13d9f4bb327f2a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354461"
---
# <a name="control-schema-should-have-header-segments-in-the-correct-order"></a>コントロールのスキーマが正しい順序でのヘッダー セグメントがあります。
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |  コントロールのスキーマは、次の順序でセグメントが必要です。ISA GS ST.SE GE IEA  |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、EDI が受信することを示します、インターチェンジに正しい順序でヘッダーと、インターチェンジ、グループ、およびトランザクション セットのトレーラーがないために、パイプラインは受信したインターチェンジを処理できませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、こと、インターチェンジに正しい順序では、ISA、GS、および ST ヘッダーと SE、GE、および IEA トレーラー、およびもらい、インターチェンジを確認します。