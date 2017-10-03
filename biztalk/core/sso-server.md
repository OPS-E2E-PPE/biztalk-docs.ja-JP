---
title: "SSO サーバー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, tasks
- Master Secret server, SSO
- servers, SSO
- SSO, servers
- SSO, Master Secret server
ms.assetid: 40240d6b-b7d1-48fb-b750-be0e380d52e3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f2f24911a0336a734125436d97dbce6f9e0b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sso-server"></a>[SSO サーバー]
エンタープライズ シングル サインオン (SSO) サーバーでは、次の作業を実行できます。  
  
-   **マスター シークレット サーバーとして機能します。** マスタ シークレット サーバーには、SSO システム内のすべての資格情報を暗号化するために使用するマスタ シークレット (キー) のコピーが保存されます。 マスタ シークレット サーバーを参照や管理のためのサーバーとして機能させることもできますが、セキュリティ上の理由から、マスタ シークレット サーバーとしてのみ使用することをお勧めします。 マスター シークレット サーバーを実行、関数の詳細については、次を参照してください。[マスター シークレット サーバー](../core/master-secret-server.md)です。  
  
-   **管理操作を実行します。** SSO 管理者は、任意のシングル サインオン サーバーを使用して、関連アプリケーションの管理、ユーザー資格情報の設定、ユーザー マッピングの管理などの管理作業を実行できます。  
  
-   **参照操作を実行します。** SSO サーバーはランタイム コンポーネントを使用して、ユーザー資格情報を参照します。  
  
-   **発行し、チケットを引き換えます。** SSO サーバーは、SSO チケットの発行と引き換えを行うこともできます。  
  
-   **パスワード同期します。** SSO サーバーでパスワード同期アダプタを作成して、管理することができます。  
  
## <a name="see-also"></a>参照  
 [SSO の使用](../core/using-sso.md)   
 [SSO のインストール](../core/installing-sso.md)