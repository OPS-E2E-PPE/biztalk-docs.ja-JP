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
ms.openlocfilehash: d45e8e983e626db3b48c4875573fd7e3a92d50e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357650"
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
|  メッセージ テキスト   | スキームの標準メタデータ バインドを作成することはできません"{0}"。 サポートされているスキームは http、https、net.pipe、および net.tcp です。 |
  
## <a name="explanation"></a>説明  
 このエラーは、メタデータが使用しようとするサービスがサポートされているスキームを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 有効なスキームでメタデータを公開し、新しいメタデータの場所に対して、もう一度ウィザードを実行します。  
  
 アダプターとバインドする方法の詳細についてで次の情報を参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [WCF アダプター](../core/wcf-adapters.md)