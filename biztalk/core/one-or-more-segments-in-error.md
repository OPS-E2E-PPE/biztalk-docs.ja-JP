---
title: 1 つまたは複数のエラー セグメント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ee86667-e72a-4f1b-8d5c-15ca710dbe5d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c364af2691767ac55a52afb52b77f09d39ef6d2d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005072"
---
# <a name="one-or-more-segments-in-error"></a>エラーに 1 つ以上のセグメントが含まれています
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                        X12TsOneOrMoreSegmentsInErrorDescription                        |
|  メッセージ テキスト   |                             エラーに 1 つ以上のセグメントが含まれています                              |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジの 1 つ以上のセグメントが、それらのセグメントを管理するスキーマに準拠していなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、どのセグメントがエラーになっているかを特定し、そのセグメントを管理するスキーマを開きます。その後、セグメントがエラーになっている理由をそのスキーマから判断します。