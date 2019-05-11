---
title: アプリケーション展開タスク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, deploying
- applications, tasks
- deploying [applications], tasks
ms.assetid: 8cb29292-9868-41fa-9f2c-d1c20dfdddbb
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da4c55063132a7115eba0f81efb5ede5c4f24df6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359059"
---
# <a name="application-deployment-tasks"></a>アプリケーション展開作業
このセクションのトピックでのアプリケーションの展開プロセスの各フェーズに関連する次のタスクについて詳しく説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]:  
  
1. **開発します。** 開発者から、BizTalk アプリケーションに含まれる BizTalk アセンブリを展開する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発用コンピューターで実行されています。 これは自動的に、アプリケーションが作成され、アセンブリに含まれるアイテムを設定します。 アーティファクトは、すべての BizTalk アセンブリ、.NET アセンブリ、スキーマ、マップ、バインド、証明書、およびなどを含む、BizTalk ビジネス ソリューションを構成する項目。 開発者は、任意の他のアイテムを追加したり、追加の構成を実行して、アプリケーションを完了します。 開発者、.msi ファイルからアプリケーションをインストール、機能を検証するためのテストを、問題を修正しからアプリケーションをエクスポートし、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .msi ファイルとして。  
  
2. **テストします。** テスターは、.msi ファイルをインポートします[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でアプリケーションを作成します。 テスト コンピューターで実行されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 テスト担当者には、.msi ファイルからのホスト コンピューター上のアプリケーションもインストールされます。 テストおよびバグの修正が完了した後、テスト担当者がからアプリケーションをエクスポートします[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].msi ファイルとして。  
  
3. **ステージングします。** IT 管理者に .msi ファイルをインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境用に構成します、ホスト コンピューターにインストール、機能を検証および完成したアプリケーションを .msi ファイルとしてエクスポートします、ステージング サーバーで実行されています。  
  
4. **実稼働します。** IT 管理者に .msi ファイルをインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]運用環境で実行されている、ホスト コンピューターにアプリケーションをインストールし、アプリケーションを起動します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk アプリケーション展開の開発作業](../core/development-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk アプリケーション展開のテスト作業](../core/testing-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk アプリケーション展開のステージング作業](../core/staging-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk アプリケーション展開の実稼働作業](../core/production-tasks-for-biztalk-application-deployment.md)