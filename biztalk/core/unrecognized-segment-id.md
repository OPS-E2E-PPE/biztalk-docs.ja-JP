---
title: セグメント ID が認識されない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a00fe451-0a84-4dca-980c-682243fc9804
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c093eb9b6793dfd4b211bff67bb51f467f2a57
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396040"
---
# <a name="unrecognized-segment-id"></a>セグメント ID が認識されません
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                       EDI エンジン                                       |
|  シンボル名  | EfactUnrecognizedSegmentIDDescription<br /><br /> X12UnrecognizedSegmentIDDescription  |
|  メッセージ テキスト   |                                セグメント ID が認識されません                                 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジのトランザクション セットのセグメントが、対応するドキュメント スキーマで定義されていなかったため、受信パイプラインが受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者に対して、認識されないセグメントを削除し、インターチェンジを再送信するように依頼します。