---
title: SSO 展開の概要 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, deploying example
- SSO, deploying
- deploying, SSO
- SSO, multiple computers
- examples, deploying
ms.assetid: 6eccee26-c392-41fe-97fb-3afe1685540f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c942bf7f7fd0853164e2cf2b8fdadbfced2fe33d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401753"
---
# <a name="sso-deployment-overview"></a>SSO 展開の概要
この例では、システムは、次のコンピューターを含む、3 つのドメインに展開されます。  
  
 **ドメイン ORCH.com**  
  
- ORCH ドメイン コントローラ  
  
- HIS1、HISSO サーバー  
  
- HIS2、マスタ シークレット サーバー  
  
- HIS3、管理データベース  
  
  **ドメイン SQL.com**  
  
- SQL ドメイン コント ローラー  
  
- SQL2、SSO データベース  
  
  **ドメイン HIS.com**  
  
- 自分のドメイン コントローラ  
  
- HIS4 データベース  
  
  この配置を定義する重要な点は次のとおりです。  
  
- ドメイン ORCH.com とドメイン SQL.com 選択的な双方向の信頼関係があります。  
  
- ドメイン ORCH.com はネイティブとして構成されている[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]の機能レベル。  
  
- ORCH.com ドメイン ユーザー アカウント (orch \ssosvcuser) では、すべての SSO サービスが実行されています。 ユーザーは、SQL.com ドメイン内の SQL2 コンピュータに対するアクセス許可が構成されます。 ユーザーは、プロトコル遷移用に構成され、ORCH.com ドメイン内での委任を制限します。  
  
- ORCH.com のもう 1 つのドメイン ユーザー (orch \testappuser) は、テスト プログラムを実行するために設定されています。 このユーザーは、プロトコル遷移用に設定し、制約付き委任します。  
  
## <a name="see-also"></a>参照  
 [展開プロセス](../core/deployment-process.md)