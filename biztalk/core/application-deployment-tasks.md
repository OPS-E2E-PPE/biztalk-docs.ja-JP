---
title: アプリケーション展開作業 |Microsoft ドキュメント
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
ms.openlocfilehash: ed5dd5b2a15bd8408ee11934d7dd6274e81651b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230426"
---
# <a name="application-deployment-tasks"></a>アプリケーション展開作業
このセクションのトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] におけるアプリケーション展開プロセスの各フェーズに関連する次の作業の詳細について説明します。  
  
1.  **開発します。** 開発者から BizTalk アプリケーションに含まれる BizTalk アセンブリを展開する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発用コンピューターで実行されています。 これにより、自動的にアプリケーションが作成され、アセンブリに含まれているアイテムがこのアプリケーションに設定されます。 アイテムは、BizTalk アセンブリ、.NET アセンブリ、スキーマ、マップ、バインド、証明書など、BizTalk ビジネス ソリューションを構成するすべての項目です。 開発者は、アプリケーションに追加可能なアイテムを追加したり、追加の構成を実行して、アプリケーションを完了させます。 続いて、.msi ファイルからアプリケーションをインストールし、機能を検証するためのテストを実行して問題を修正し、.msi ファイルとして [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からアプリケーションをエクスポートします。  
  
2.  **テストします。** テスターは、.msi ファイルをインポート[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でアプリケーションを作成するテスト コンピューターで実行されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 また、テスターは、ホスト コンピューターにも .msi ファイルからアプリケーションをインストールします。 テストを実行してバグの修正が完了すると、テスターはアプリケーションを .msi ファイルとして [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からエクスポートします。  
  
3.  **ステージングします。** IT 管理者に .msi ファイルをインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境用に構成、ホスト コンピューターにインストール、して機能検証およびし、完成したアプリケーションを .msi ファイルとしてエクスポート、ステージング サーバー上で実行します。  
  
4.  **実稼働します。** IT 管理者に .msi ファイルをインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境で実行されているホスト コンピューターにアプリケーションをインストールししてアプリケーションを起動します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk アプリケーション展開の開発タスク](../core/development-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk アプリケーションの展開のテスト作業](../core/testing-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk アプリケーションの展開のステージング作業](../core/staging-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk アプリケーションの展開の実稼働作業](../core/production-tasks-for-biztalk-application-deployment.md)