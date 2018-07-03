---
title: クロス フィールド検証規則に違反しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d606a80-9046-4572-9cfb-a3434ed8073e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d590fc318e7d833a067f4275986bef88da10364
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976659"
---
# <a name="cross-field-validation-rule-violated"></a>クロス フィールド検証規則に違反しました
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                                           -                                            |
|  メッセージ テキスト   |                          クロス フィールド検証規則に違反しました                          |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、X12 インターチェンジが受信パイプラインまたは送信パイプラインでのクロスフィールド検証に失敗したことを示します。 これは、X12ConditionDesignator_Check フラグが "Yes" に設定されていて、インターチェンジの少なくとも 1 つの要素が、接頭辞 "X12ConditionDesignatorX" によって識別されたルールに違反していることを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   どのデータ要素がクロスフィールド検証ルールに違反しているかを特定します。 インターチェンジの送信者に連絡を取り、インターチェンジを作成するときはルールに従う必要があることを通知します。  
  
-   インターチェンジのスキーマを開き、検証に失敗したデータ要素の X12ConditionDesignator_Check フラグを "No" に設定します。