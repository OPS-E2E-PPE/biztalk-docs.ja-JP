---
title: "カスタム コンポーネントの開発 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 12b7d99d-ac3c-427d-b6b6-286233fde541
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b61144b2acaf787d56468c23c04835b5ad79324
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="developing-custom-components"></a>カスタム コンポーネントの開発
BizTalk Server のカスタム コンポーネントは、BizTalk Server の特定のインフラストラクチャ要素を変更または拡張するために開発および使用されます。  主などが含まれます: 送信または受信アダプターはアダプター フレームワークに基づいており、特定のトランスポート プロトコルを処理するために使用します。送信のいずれかで使用されるコンポーネントをパイプラインまたは受信パイプラインのステージです。および functoid のマップで使用します。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をカスタム コードで拡張するには、いくつかの方法があります。 この方法については、以下のトピックで説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [カスタム アダプターの開発](../core/developing-custom-adapters.md)  
  
-   [カスタム パイプライン コンポーネントの開発](../core/developing-custom-pipeline-components.md)  
  
-   [カスタム Functoid の開発](../core/developing-custom-functoids.md)