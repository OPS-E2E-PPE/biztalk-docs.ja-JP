---
title: プロトコルが無効にに対して見つかったアグリーメントの状態を期限切れまたは |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b524f423-1325-495c-9499-33101f6388fc
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d7e4092b057b83caef252d63853ecf6791edbde
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014723"
---
# <a name="agreement-found-for-the-protocol-is-in-disabled-or-expired-state"></a>プロトコルに対して見つかったアグリーメントの状態が "無効" または "期限切れ" です
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                     AgreementResolutionAgreementDiasbledOrExpired                      |
|  メッセージ テキスト   |      アグリーメントが見つかりませんでした、{0}プロトコルが無効または期限切れのいずれかの状態。      |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server がアグリーメントを解決できたが、アグリーメントの状態が無効または期限切れだったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、アグリーメントを有効にしてください。