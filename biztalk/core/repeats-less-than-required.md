---
title: 必要なよりも少ない繰り返されます |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5bebc13-0e70-4f73-99c0-fed917d79fba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb28a11b7f13ab12819bc474af26653051c112bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397907"
---
# <a name="repeats-less-than-required"></a>繰り返しが必要な回数を下回っています
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                        X12FeRepeatsLessThanRequiredDescription                         |
|  メッセージ テキスト   |                               繰り返しが必要な回数を下回っています                               |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、X12 インターチェンジのループ内またはループ外にあるセグメントの繰り返しが、ドキュメント スキーマで必要な回数を下回っていたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのループの内側または外側にあるセグメントがスキーマで指定された回数繰り返されることを確認し、インターチェンジを再送信します。