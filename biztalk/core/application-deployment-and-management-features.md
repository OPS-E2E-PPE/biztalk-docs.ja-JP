---
title: アプリケーションの展開と管理機能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- what's new, Installation Wizard
- what's new, BTSTask command-line tool
- what's new, Import Wizard
- deploying, what's new
- what's new, Export Wizard
- what's new, deploying
- applications, what's new
- what's new, applications
ms.assetid: 2d09d6b1-1003-406f-81da-14e21a1cbc81
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb5258868e5c2c023be1a4a41f001b48d35a5c72
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359090"
---
# <a name="application-deployment-and-management-features"></a>アプリケーションの展開および管理の機能
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、BizTalk ビジネス ソリューションの展開を支援するための機能が用意されています。  
  
- **BizTalk アプリケーション。** BizTalk アプリケーションは、BizTalk Server ビジネス ソリューションを構成する "アイテム" を表示して管理する機能を提供します。 アイテムには、アセンブリ、オーケストレーション、マップ、スキーマ、セキュリティ証明書、ビジネス ルール ポリシー、BAM 構成ファイル、バインド、スクリプトなどビジネス ソリューションが機能するために必要な要素が含まれます。 BizTalk アプリケーションにアイテムを追加して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソール内から、アプリケーションのすべてのアイテムを 1 つのエンティティとして表示、パッケージ化、展開、および管理することができます。 1 つまたは複数の BizTalk アプリケーションを作成して、ビジネス ソリューションのアイテムを管理できます。 エクスポート ウィザードを使用してアプリケーションやそのアイテムをエクスポートし、インポート ウィザードを使用して、.msi を別の BizTalk グループにインポートして再作成することができます。 さらに、インストール ウィザードを使用して、アプリケーションをインストールできます。 これらのウィザードについては、このトピックの後半で説明します。 このドキュメント内の展開手順には、それぞれ管理コンソールの使用手順が含まれています。 BTSTask コマンド ライン ツールを使用してさまざまな管理タスクを実行することも可能で、このドキュメントでは、BTSTask の使用手順についても説明します。  
  
- **ウィザードをインポートします。** 利用できるインポート ウィザードを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、BizTalk アプリケーションにアイテムを .msi ファイルからインポートします。 指定したアプリケーションがまだ存在しない場合は、インポート ウィザードによって作成されます。 また、このウィザードによって、.msi ファイル内のアイテムが BizTalk 管理データベースに登録され保存されます。 インポート ウィザードを使用して、アイテムのインポートの詳細については、次を参照してください。[をインポートする BizTalk アプリケーション、バインド、およびポリシー](../core/importing-biztalk-applications-bindings-and-policies.md)します。  
  
- **インストール ウィザード。** インストール ウィザードは、インポート ウィザードの最後に起動することができます。 このウィザードは、ローカル コンピューターのアプリケーションを実行できるように、ローカル コンピューターでは、アプリケーションをインストールします。 手順については、次を参照してください。 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。 インポート ウィザードは、.msi ファイルをダブルクリックすることでも開始できます。 詳細については、次を参照してください。 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。  
  
- **ウィザードをエクスポートします。** エクスポート ウィザードは、BizTalk Server 管理コンソールから利用でき、BizTalk アプリケーションから .msi ファイルを生成するために使用します。 その後、インポート ウィザードを使用してこの .msi ファイルを別の BizTalk グループにインポートできます。 これにより、アプリケーションにリソースを簡単に追加したり、新しい BizTalk グループにアプリケーションを自動的に作成することができます。 エクスポート ウィザードの使用方法の詳細については、次を参照してください。 [BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。  
  
- **BTSTask コマンド ライン ツールです。** BTSTask のアプリケーション展開機能をサポートしている[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、コマンドラインから多くの操作を実行することができます。 詳細については、次を参照してください。 [BTSTask コマンド ライン リファレンス](../core/btstask-command-line-reference.md)します。  
  
  これらのアプリケーション展開機能に慣れるために、お勧めの手順を実行する[チュートリアル。基本的な BizTalk アプリケーション展開](../core/walkthrough-deploying-a-basic-biztalk-application.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの展開と管理について](../core/understanding-biztalk-application-deployment-and-management.md)