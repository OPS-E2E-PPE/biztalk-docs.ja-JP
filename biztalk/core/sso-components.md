---
title: SSO コンポーネント |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- passwords, synchronizing [SSO]
- SSO, components
- SSO, password synchronization
- SSO, sub-services
ms.assetid: e29e68df-f770-4220-a9f8-cb9323403017
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e7e00ad4dfb82d2c6e16c45a09c4f452b33081b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401758"
---
# <a name="sso-components"></a>SSO コンポーネント
エンタープライズ シングル サインオン (SSO) service のサブサービスは次のとおりです。  
  
-   **マッピングします。** このコンポーネントは、バックエンド システムでユーザー アカウントを Windows システムでユーザー アカウントをマップします。  
  
-   **参照します。** このコンポーネントは、バックエンド システムでは、SSO データベース内のユーザーの資格情報を検索します。 これは、SSO ランタイム コンポーネントです。  
  
-   **管理します。** このコンポーネントは、関連アプリケーションと関連アプリケーションごとのマッピングを管理します。  
  
-   **シークレット。** このコンポーネントは、マスター シークレットを生成し、システム内の他の SSO サーバーに配布します。 マスター シークレット サーバーとして動作しているシングル サインオン サーバーでアクティブなだけです。  
  
-   **パスワード同期します。** このコンポーネントは、SSO データベースの管理を簡略化し、ユーザー ディレクトリ間でパスワード同期を保ちます。  
  
## <a name="see-also"></a>参照  
 [SSO サーバー](../core/sso-server.md)   
 [SSO のインストール](../core/installing-sso.md)