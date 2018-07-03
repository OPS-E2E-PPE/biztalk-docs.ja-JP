---
title: スキームの標準メタデータ バインドを作成することはできません |Microsoft Docs
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
ms.openlocfilehash: 4fd4a91535c7872bb5be7328755808eb91758db6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989315"
---
# <a name="cannot-create-standard-metadata-binding-for-scheme"></a>スキームの標準メタデータ バインドを作成できません
## <a name="details"></a>詳細  
  
|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  製品名   |                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                 |
| 製品バージョン |                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                             |
|    イベント ID     |                                                         0                                                          |
|  イベント ソース   |                                                         0                                                          |
|    コンポーネント    |                                                         0                                                          |
|  シンボル名  |                                                         0                                                          |
|  メッセージ テキスト   | スキームの標準メタデータ バインドを作成することはできません"{0}"。 サポートされているスキームは、http、https、net.pipe、および net.tcp です。 |
  
## <a name="explanation"></a>説明  
 このエラーは、使用するメタデータのサービスは、サポートされたスキームではないことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 有効なスキームでメタデータを公開し、新しいメタデータの場所に対して、ウィザードをもう一度実行します。  
  
 アダプターおよびバインドの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [WCF アダプター](../core/wcf-adapters.md)