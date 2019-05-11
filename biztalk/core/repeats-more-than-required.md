---
title: 必要な複数の繰り返し |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fec52b5b-e95f-479e-8922-dcf17dcefee7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d241e357425f18f6a378dc3dba9a2ffbd32c3ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397896"
---
# <a name="repeats-more-than-required"></a>繰り返しが必要な回数を上回っています
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                        X12FeRepeatsMoreThanRequiredDescription                         |
|  メッセージ テキスト   |                               繰り返しが必要な回数を上回っています                               |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、X12 インターチェンジのループ内またはループ外にあるセグメントの繰り返しが、ドキュメント スキーマで必要な回数を上回っていたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジのループの内側または外側にあるセグメントがスキーマで指定された回数繰り返されることを確認し、インターチェンジを再送信します。