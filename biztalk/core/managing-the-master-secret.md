---
title: マスタ シークレットの管理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, managing
- managing [Master Secret server]
- SSO, Master Secret server
ms.assetid: f79e8f3f-c740-4ea1-9589-b42552fcd52d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2505fa6f5ec1abc04ded45e7701fd4e5212f889
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262178"
---
# <a name="managing-the-master-secret"></a>マスタ シークレットの管理
マスタ シークレットは、SSO データベースに格納されているすべての情報を暗号化するために使用されるキーです。 マスタ シークレット サーバーに障害が発生してマスタ シークレットが失われると、SSO データベースに格納されている情報を取得できなくなります。 そのため、マスタ シークレットは作成したらすぐにバックアップすることが重要です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  
  
-   [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)  
  
-   [マスター シークレットを復元する方法](../core/how-to-restore-the-master-secret.md)  
  
-   [マスター シークレット サーバーを移動する方法](../core/how-to-move-the-master-secret-server.md)