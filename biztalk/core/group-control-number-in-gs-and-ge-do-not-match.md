---
title: GS と GE のグループ制御番号が一致しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2419f61-2717-4347-a4be-54362330c7e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d2e08bf3520b1a1b10abd66059e037fe258ec3c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344885"
---
# <a name="group-control-number-in-gs-and-ge-do-not-match"></a>GS と GE のグループ制御番号が一致しません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  |                         X12FaControlNumberMismatchDescription                          |
|  メッセージ テキスト   |                     GS と GE のグループ制御番号が一致しません                     |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジの GS06 および GE02 フィールドに含まれている制御番号の値が同じでないため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの GS06 および GE02 フィールドに含まれているグループ制御番号の値が同じであることを確認し、インターチェンジを再送信してもらいます。