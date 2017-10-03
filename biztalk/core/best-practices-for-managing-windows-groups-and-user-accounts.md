---
title: "Windows グループとユーザー アカウントを管理するためのベスト プラクティス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, Windows groups
- authenticating, best practices
- Windows groups, security
- best practices, user accounts
- best practices, security
- security, best practices
- user accounts, security
- authenticating, security
- Windows groups, best practices
- best practices, authenticating
- user accounts, best practices
- hosts, security
- hosts, best practices
- best practices, hosts
ms.assetid: 0c4a141e-97ce-434a-8e45-a56c634bbd6c
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 71f7560e3867bf290f20e0f2f49a740d7298131b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-managing-windows-groups-and-user-accounts"></a>Windows グループおよびユーザー アカウントの管理のベスト プラクティス
このセクションでは、Windows グループおよびユーザー アカウントのセキュリティ管理のベスト プラクティスおよびヒントについて説明します。  
  
-   **サービス アカウントのホスト インスタンスに必要な最低限の特権を使用します。**  
  
     BizTalk Server 環境のセキュリティを確保するには、ホスト インスタンスの実行に必要な最小限の権限を持つサービス アカウントを使用することをお勧めします。 サービス アカウントに必要な最低限の特権の詳細については、次を参照してください。[アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)です。  
  
-   **信頼されている認証および信頼されていないホストに別のユーザー グループを使用します。**  
  
     信頼されていない認証ホストの権限が、信頼済み認証ホストの権限よりも低くなるように、各ホストに別々のサービス アカウントを使用する必要があります。  
  
-   **各 BizTalk ホストの別のユーザー グループを使用します。**  
  
     ホスト間のセキュリティ境界を最大限に高めるには、BizTalk グループ内の各 BizTalk ホストに対して、別々の Windows ユーザー グループを使用することをお勧めします。  
  
-   **BizTalk Server 管理者グループからインストール ユーザーを削除します。**  
  
     複数のローカル グループがある 1 台のコンピュータに BizTalk Server をインストールすると、BizTalk Server の対話型インストールを実行しているユーザーは、BizTalk Server 管理者グループに自動的に追加されます。 これによりユーザーは、構成マネージャで BizTalk Server を構成できます。  
  
     BizTalk Server をインストールしたユーザーが BizTalk Server の管理担当ではない場合、BizTalk Server を構成した後で、このユーザーを BizTalk Server 管理者グループから削除することをお勧めします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のセキュリティを管理します。](../core/managing-biztalk-server-security.md)