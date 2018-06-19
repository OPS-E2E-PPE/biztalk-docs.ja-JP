---
title: スキームの標準メタデータ バインドを作成することはできません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce441c3e-0f6e-46ed-90cf-825dbf89d910
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3228da0dfee18581c5fa8105ce3dd480380cc034
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231170"
---
# <a name="cannot-create-standard-metadata-binding-for-scheme"></a>スキームの標準メタデータ バインドを作成できません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|スキーム "{0}" の標準メタデータ バインドを作成できません。 サポートされているスキームは、http、https、net.pipe、および net.tcp です。|  
  
## <a name="explanation"></a>説明  
 このエラーは、使用するメタデータのサービスは、サポートされたスキームではないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 有効なスキームでメタデータを公開し、新しいメタデータの場所に対して、ウィザードをもう一度実行します。  
  
 アダプターおよびバインドの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [WCF アダプタ](../core/wcf-adapters.md)