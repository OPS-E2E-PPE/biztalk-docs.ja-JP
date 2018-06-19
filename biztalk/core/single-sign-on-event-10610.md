---
title: 'シングル サインオン: イベント 10610 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6a400eb-7cf2-49df-befb-caf76e845fdf
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3e4edc579c18147ad34234fbf268ec8d867c60f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271338"
---
# <a name="single-sign-on-event-10610"></a>シングル サインオン: イベント 10610
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10610|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_CRED_CACHE_FAILED|  
|メッセージ テキスト|資格情報キャッシュに予期しないエラーが発生し、シャットダウンされました。 パフォーマンスが低下する場合があります。%r<br /><br /> エラー コード: %1|  
  
## <a name="explanation"></a>説明  
 資格情報キャッシュに予期しないエラーが発生し、シャットダウンされました。 これによってパフォーマンスは低下する場合がありますが、機能への影響はありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 適切なときに SSO サービスを再起動します。