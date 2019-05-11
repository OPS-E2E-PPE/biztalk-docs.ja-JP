---
title: 企業用のポートのシングル サインオン サーバー |Microsoft Docs
ms.custom: ''
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, SSO
- SSO
ms.assetid: 30eb99f9-02cb-43c9-b038-d7bd898e3a7a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e5070fffd9cb6de3e058cd9f2db4612e5bb147a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394853"
---
# <a name="ports-for-the-enterprise-single-sign-on-servers"></a>エンタープライズ シングル サインオン サーバーのポート
BizTalk Server の展開をセキュリティで保護する方法の詳細については、「 [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)」を参照してください。  
  
 次の表は、処理ドメイン内のエンタープライズ シングル サインオン サーバーがマスター シークレット サーバーおよび SSO データベースにアクセスする必要があるポートを一覧表示します。 これらのポートは、入力トラフィックと出力トラフィックの両方に対して開く必要があります。  
  
|サービスまたはアプリケーションのコンテキスト|[同期先サーバー]|対象のサービス|Port|プロトコル|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|ログオン ユーザー|SSO データベース|SQL Server|1433|TCP|作成し、SSO データベースに接続します。|  
|シングル サインオン サービス アカウント|[マスター シークレット サーバー]|シングル サインオン サービス|135|TCP|マスター シークレット サーバーからマスター シークレット キーを取得する、シングル サインオン サービス用の SQL Server への接続をトランザクション|  
|シングル サインオン サービス アカウント|[マスター シークレット サーバー]|シングル サインオン サービス|50000-50200|TCP|セカンダリ RPC ポートをマスター シークレット サーバーからシークレット キーを取得するために使用します。 **注:** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
  
 次の表は、ポートが必要なサービスにアクセスするエンタープライズ シングル サインオン (SSO) マスター シークレット サーバーを構成する必要があります。 ポートを開く必要があるファイアウォールは、対象のサーバーがアーキテクチャ内のどこに配置されているのかによって異なります。 これらのポートは、入力トラフィックと出力トラフィックの両方に対して開く必要があります。  
  
|サービスまたはアプリケーションのコンテキスト|[同期先サーバー]|対象のサービス|Port|プロトコル|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|ログオン ユーザー|SSO データベース|SQL Server|1433|TCP|作成し、SSO データベースに接続します。|  
|シングル サインオン サービス アカウント|サーバーの処理|シングル サインオン サービス|135|TCP|マスター シークレット サーバーからマスター シークレット キーを取得する、シングル サインオン サービス用の SQL Server への接続をトランザクション|  
|シングル サインオン サービス アカウント|サーバーの処理|シングル サインオン サービス|50000-50200|TCP|セカンダリ RPC ポートをマスター シークレット サーバーからシークレット キーを取得するために使用します。 **注:** サーバーの負荷によって複数のセカンダリ RPC ポートを開く必要があります。|  
  
## <a name="see-also"></a>参照  
 [サーバーの名前付け規則](../core/server-naming-conventions.md)   
 [SSO のセキュリティに関する推奨事項](../core/sso-security-recommendations.md)   
 [インフォメーション ワーカー サービスで大規模な分散アーキテクチャ](../core/large-distributed-architecture-with-information-worker-services.md)   
 [BizTalk Server に必要なポート](../core/required-ports-for-biztalk-server.md)