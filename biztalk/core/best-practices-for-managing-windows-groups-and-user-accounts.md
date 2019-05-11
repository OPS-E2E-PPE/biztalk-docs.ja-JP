---
title: Windows グループとユーザー アカウントを管理するためのベスト プラクティス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6720135f15b2c6d50bb193cd6e533e5b06f71961
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358202"
---
# <a name="best-practices-for-managing-windows-groups-and-user-accounts"></a>Windows グループとユーザー アカウントを管理するためのベスト プラクティス
このセクションには、ベスト プラクティスや Windows グループとユーザー アカウントのセキュリティを管理するためのヒントが含まれています。  
  
-   **ホスト インスタンスに必要な最小限の特権を使用してサービス アカウント**  
  
     BizTalk Server 環境のセキュリティを確保するには、ホスト インスタンスを実行するために必要な最小限の特権をサービス アカウントを使用することをお勧めします。 サービス アカウントに必要な最低限の特権の詳細については、次を参照してください。[アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)します。  
  
-   **信頼された認証と信頼されていないホストの別のユーザー グループを使用します。**  
  
     ホストが信頼されたホストの認証よりも少ない特権を持つその非認証が信頼されていることを確認するには、ホストごとに異なるサービス アカウントを使用する必要があります。  
  
-   **各 BizTalk ホストの別のユーザーのグループを使用します。**  
  
     ホスト間のセキュリティ境界を最大化するには、BizTalk グループで、各 BizTalk ホストの別の Windows ユーザー グループを使用することをお勧めします。  
  
-   **BizTalk Server 管理者グループからのインストール ユーザーを削除します。**  
  
     ローカル グループを含む 1 台のコンピューターに BizTalk Server をインストールすると、BizTalk Server の対話型インストールを実行するユーザーは、BizTalk Server 管理者グループに自動的に追加します。 これにより、Configuration Manager での BizTalk Server を構成するには、そのユーザーができます。  
  
     BizTalk Server をインストールしたユーザーには BizTalk Server が管理するされない場合、は、BizTalk Server を構成した後、このユーザーを BizTalk Server 管理者グループから削除することをお勧めします。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server のセキュリティの管理](../core/managing-biztalk-server-security.md)