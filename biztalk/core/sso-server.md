---
title: SSO サーバー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, tasks
- Master Secret server, SSO
- servers, SSO
- SSO, servers
- SSO, Master Secret server
ms.assetid: 40240d6b-b7d1-48fb-b750-be0e380d52e3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a17d3ad69ab18e9d1916f5a7cf2907021d7d54c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398985"
---
# <a name="sso-server"></a>SSO サーバー
エンタープライズ シングル サインオン (SSO) サーバーは、次のタスクを実行できます。  
  
-   **マスター シークレット サーバーとして機能します。** マスター シークレット サーバーは、マスター シークレットの永続化されたコピーを保持またはキー、SSO システムですべての資格情報を暗号化するために使用します。 ただし、マスター シークレット サーバーでの検索および管理サーバーとして機能できますは、このサーバーを使用して、セキュリティ上の理由からマスター シークレット サーバーとしてのみ機能することをお勧めします。 マスター シークレット サーバーを実行、関数の詳細については、次を参照してください。[マスター シークレット サーバー](../core/master-secret-server.md)します。  
  
-   **管理操作を実行します。** SSO 管理者は関連のアプリケーションの管理などの管理タスクを実行するシングル サインオン サーバーのいずれかを使用できるユーザー資格情報を設定してユーザー マッピングを管理します。  
  
-   **参照操作を実行します。** SSO サーバーは、ユーザーの資格情報を検索するランタイム コンポーネントを使用します。  
  
-   **問題およびチケットの引き換えを行います。** SSO サーバーの発行もと SSO チケットの引き換え。  
  
-   **パスワード同期します。** 作成し、SSO サーバーでパスワード同期アダプタを管理します。  
  
## <a name="see-also"></a>参照  
 [SSO を使用してください。](../core/using-sso.md)   
 [SSO のインストール](../core/installing-sso.md)