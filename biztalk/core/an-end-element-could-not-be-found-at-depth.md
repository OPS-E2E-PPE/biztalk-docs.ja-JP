---
title: 深さの終了要素が見つかりませんでした |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1edb60a-122a-4fe9-8d73-96521fe7326b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91c2727be39d3d2656e118d593b0347038657f61
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970187"
---
# <a name="an-end-element-could-not-be-found-at-depth"></a>深さの終了要素が見つかりませんでした
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                               EndElementNotFoundAtDepth                                |
|  メッセージ テキスト   |                     深さの終了要素{0}は見つかりませんでした                     |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、XML メッセージの検証に失敗したため、BizTalk Server が送信インターチェンジを処理できなかったことを示します。 XML メッセージに、ヘッダーまたはデータ要素の終了タグが含まれていませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、XML メッセージに適切な終了タグまたはトレーラーを追加し、再送信します。