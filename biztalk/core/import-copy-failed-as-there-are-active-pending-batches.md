---
title: "アクティブな保留中のバッチがあるインポート コピーに失敗しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17803f0a-3c70-4a8a-8e8d-7f874ed9ad92
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3055f3e95ef3d0fb8bf5a36dae5957e318f6e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="import-copy-failed-as-there-are-active-pending-batches"></a>アクティブな保留中のバッチがあるインポート コピーに失敗しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|Err_ActiveBatchFound|  
|メッセージ テキスト|アクティブ状態または保留中のバッチがあるため、インポートまたはコピーはできませんでした アクティブ状態または保留中のバッチを停止してから、インポートまたはコピーを再試行してください。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、影響を受けるアグリーメントに 1 つ以上のアクティブ状態または保留中のバッチがあるため、BizTalk Server がバインド ファイルをインポートできなかったか、設定をコピーできなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、影響を受けるアグリーメントのすべてのバッチが [アグリーメントのプロパティ] で [停止] と表示されていることを確認します。