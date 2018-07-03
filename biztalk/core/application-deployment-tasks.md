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
ms.openlocfilehash: 1bffe3490571d838f9b6995ff0919fd9c0d6383a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999619"
---
# <a name="application-deployment-tasks"></a>アプリケーション展開作業
このセクションのトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] におけるアプリケーション展開プロセスの各フェーズに関連する次の作業の詳細について説明します。  
  
1. **開発します。** 開発者から、BizTalk アプリケーションに含まれる BizTalk アセンブリを展開する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]に[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]開発用コンピューターで実行されています。 これにより、自動的にアプリケーションが作成され、アセンブリに含まれているアイテムがこのアプリケーションに設定されます。 アイテムは、BizTalk アセンブリ、.NET アセンブリ、スキーマ、マップ、バインド、証明書など、BizTalk ビジネス ソリューションを構成するすべての項目です。 開発者は、アプリケーションに追加可能なアイテムを追加したり、追加の構成を実行して、アプリケーションを完了させます。 続いて、.msi ファイルからアプリケーションをインストールし、機能を検証するためのテストを実行して問題を修正し、.msi ファイルとして [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からアプリケーションをエクスポートします。  
  
2. **テストします。** テスターは、.msi ファイルをインポートします[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]でアプリケーションを作成します。 テスト コンピューターで実行されている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 また、テスターは、ホスト コンピューターにも .msi ファイルからアプリケーションをインストールします。 テストを実行してバグの修正が完了すると、テスターはアプリケーションを .msi ファイルとして [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] からエクスポートします。  
  
3. **ステージングします。** IT 管理者に .msi ファイルをインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]実稼働環境用に構成します、ホスト コンピューターにインストール、機能を検証および完成したアプリケーションを .msi ファイルとしてエクスポートします、ステージング サーバーで実行されています。  
  
4. **実稼働します。** IT 管理者に .msi ファイルをインポートする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]運用環境で実行されている、ホスト コンピューターにアプリケーションをインストールし、アプリケーションを起動します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk アプリケーション展開の開発作業](../core/development-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk アプリケーション展開のテスト作業](../core/testing-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk アプリケーション展開のステージング作業](../core/staging-tasks-for-biztalk-application-deployment.md)  
  
-   [BizTalk アプリケーション展開の実稼働作業](../core/production-tasks-for-biztalk-application-deployment.md)