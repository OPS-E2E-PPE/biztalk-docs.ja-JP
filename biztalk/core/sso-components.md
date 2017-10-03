---
title: "SSO コンポーネント |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- passwords, synchronizing [SSO]
- SSO, components
- SSO, password synchronization
- SSO, sub-services
ms.assetid: e29e68df-f770-4220-a9f8-cb9323403017
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1111f1a0dfac47412ae28b58f93ddc51e1f562b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="sso-components"></a>SSO コンポーネント
エンタープライズ シングル サインオン (SSO) サービスには、次のサブサービスがあります。  
  
-   **マッピングです。** Windows システムのユーザー アカウントをバックエンド システムのユーザー アカウントにマップします。  
  
-   **参照です。** バックエンド システムの SSO データベースに格納されているユーザーの資格情報を検索します。 これは SSO ランタイム コンポーネントです。  
  
-   **管理します。** 関連アプリケーションと各関連アプリケーションのマッピングを管理します。  
  
-   **シークレット。** マスタ シークレットを生成し、システム内の他の SSO サーバーにマスタ シークレットを配布します。 マスタ シークレットは、マスタ シークレット サーバーとして機能しているシングル サインオン サーバーでのみアクティブになります。  
  
-   **パスワード同期します。** SSO データベースの管理を簡略化し、ユーザー ディレクトリ間でパスワードを常に同期した状態で保ちます。  
  
## <a name="see-also"></a>参照  
 [SSO サーバー](../core/sso-server.md)   
 [SSO のインストール](../core/installing-sso.md)