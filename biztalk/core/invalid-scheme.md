---
title: "無効なスキーム |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bb3e70a-d23c-45e9-bde5-edae6731e58a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5736a3738a9598f4c4b419d7e291c3c3e32207f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-scheme"></a>スキームが無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|無効なスキームです。スキーム"{0}"または「{1}」を指定してください。|  
  
## <a name="explanation"></a>説明  
 次のいずれかが発生しました。 URI (uniform リソース識別子) フィールドに指定されているアドレスが http://または https://で開始する必要があります。 または、スキームが、トランスポート バインディング要素の実装で指定されているスキームと一致しません。  
  
## <a name="user-action"></a>ユーザーの操作  
 http:// または https:// から始まる有効なプロキシ アドレスの URI を入力します