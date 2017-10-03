---
title: "シリアル化中にルート ノードがない開始要素に配置 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ea4aa6f-0f9c-4b7b-b7f6-24a5ce954048
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3dced7e36802dd9d9ec9620272fc8a96bd6b590
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="during-serialization-root-node-is-not-placed-at-start-element"></a>シリアル化中にルート ノードが開始要素に配置されません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|-|  
|メッセージ テキスト|シリアル化中にルート ノードが開始要素に配置されません|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セットが ST または UNH ヘッダーで始まらないため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの各トランザクション セットが ST セグメント (X12 インターチェンジの場合) または UNH セグメント (EDIFACT インターチェンジの場合) で始まることを確認し、インターチェンジを再送信します。