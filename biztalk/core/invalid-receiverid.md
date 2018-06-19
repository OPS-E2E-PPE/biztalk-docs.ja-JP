---
title: Receiverid が無効です |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: feabf940-c49b-4f4a-8906-230dc8fb1b30
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d397c75efe1172f87def3dee92e20f4d0d7ef4d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257058"
---
# <a name="invalid-receiverid"></a>ReceiverId が無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12Ta1InvalidReceiverIdDescription|  
|メッセージ テキスト|ReceiverId が無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、ISA08 フィールドの受信者 ID または UNB3.1 フィールドの受信者 ID が、サービス スキーマ (BaseArtifacts.dll 内の X12ServiceSchema または EdifactServiceSchema) で設定されたデータ型と桁数に準拠していなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、ISA08 フィールドが X12_AN データ型で、長さが 15 桁 (末尾のスペースの有無とは無関係) であるか、または UNB3.1 フィールドが EDIFACT_AN データ型で、長さが 1 ～ 35 文字の範囲であることを確認します。 インターチェンジを再送信します。