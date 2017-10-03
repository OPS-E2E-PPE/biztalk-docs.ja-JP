---
title: "無効なテスト インジケーターの値 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d81d501-4020-4ff9-955c-5674a99d250b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 166ab446831243c58b1c12881393be1466399e0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-test-indicator-value"></a>テスト インジケーターの値が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12Ta1InvalidTestIndicatorValueDescription|  
|メッセージ テキスト|テスト インジケーターの値が無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、UNB11 フィールドのテスト インジケーターがサービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で設定されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、UNB11 フィールドが EDIFACT_N データ型であり、1 文字の長さであることを確認します。 インターチェンジを再送信します。