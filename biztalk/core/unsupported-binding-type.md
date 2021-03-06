---
title: サポートされていないバインドの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5556a7d7-f092-4f69-9561-88f51ac46cc9
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6714c1acdf2f802037b8cd9509468194fee9d360
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399458"
---
# <a name="unsupported-binding-type"></a>バインドの種類はサポートされていません
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                              バインドの種類はサポートされていません                              |
  
## <a name="explanation"></a>説明  
 MsmqIntegration バインディングが選択されましたが、WCF アダプターでサポートされていません。  
  
## <a name="user-action"></a>ユーザーの操作  
 WCF-NetMsmq アダプターを使用します。 ネイティブの MSMQ メッセージを交換する必要がある場合、BizTalk MSMQ アダプターを使用します。  
  
 アダプターの構成の詳細については、次の情報を参照してください。  
  
-   [WCF-NetMsmq アダプターの構成](../core/configuring-the-wcf-netmsmq-adapter.md)