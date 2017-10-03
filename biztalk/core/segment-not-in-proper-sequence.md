---
title: "適切な順序ではなくセグメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f0c0fdc-10d9-4b77-a80d-b2b8571e7665
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b6147ea32bed7adf10640a3291ea9c75f71b1e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="segment-not-in-proper-sequence"></a>適切なシーケンスにセグメントがありません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12SegmentNotInProperSequenceDescription|  
|メッセージ テキスト|適切なシーケンスにセグメントがありません|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジのセグメントが、ドキュメント スキーマで指定されたシーケンスの範囲外であるため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者に対して、インターチェンジのセグメントを並べ替え、ドキュメント スキーマで指定されている順序になるようにして、インターチェンジを再送信するように依頼します。