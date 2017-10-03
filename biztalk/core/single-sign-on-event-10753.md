---
title: "シングル サインオン: イベント 10753 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b538083-180b-4a15-bedf-aac4fc351c30
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6fc43f8ffba195b7a0156a9004d140f1e3c585db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10753"></a>シングル サインオン: イベント 10753
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10753|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_MAPPING_EXISTS|  
|メッセージ テキスト|マッピングは既に存在します。|  
  
## <a name="explanation"></a>説明  
 このマッピングは、使用中の Windows アカウントまたは外部アカウントに既に存在しています。  
  
## <a name="user-action"></a>ユーザーの操作  
 既存のマッピングおよび作成しようとしているマッピングを確認します。 必要なマッピングが既に存在している場合は、そのマッピングを使用し、新しいマッピングを削除します。 マッピングが存在しない場合は、新しいマッピングを削除して作成し直します。