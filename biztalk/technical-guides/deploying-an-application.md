---
title: アプリケーションの配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04bb4496-b1e9-400b-a849-a355381849ff
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2eea66cda073317cfaa1ed3458950e7edfbd698
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266422"
---
# <a name="deploying-an-application"></a>アプリケーションを展開します。
展開では、必要なすべてのコンポーネントを必要とするシステムに使用できるようにするアプリケーションのアイテムのロジスティック分布です。 これらの成果物には、BizTalk Server アセンブリ、.NET アセンブリ、スキーマ、マップ、バインド、ビジネス ルール、および証明書が含まれます。 成果物を (別の環境にアプリケーションを転送) するときに、グループまたはステージングのために追加する他のコンピューターに展開する BizTalk アプリケーションを利用できます。  
  
 たとえばインポートして、アプリケーションの一部としてインポートする (.msi ファイル) からの展開ウィザードを使用して BTSTask.exe を使用して、Visual Studio から配置する、または MSBuild を使用して BizTalk アイテムを展開する多くの方法はあります。 それらをインポートする場合は BTSTask.exe を使用して、それらを展開または Visual Studio からのデプロイは、アプリケーションを指定するか空白のままに、アプリケーション名、既定のアプリケーションへのデプロイ場合。  
  
## <a name="deploying-by-using-an-msi-file"></a>.Msi ファイルを使用して展開します。  
 BizTalk Server では、.msi ファイルにエクスポートして、アプリケーションとそのアイテムを展開できます。 (アプリケーションとアイテムの詳細については、次を参照してください[BizTalk アプリケーションとは何ですか?。](http://go.microsoft.com/fwlink/?LinkId=154994) (<http://go.microsoft.com/fwlink/?LinkId=154994>). BizTalk アプリケーションの展開では、アプリケーションのアイテムを BizTalk 管理データベースにインポートすると、グループのメンバーである各コンピューターで、成果物をインストールする必要があります。 .Msi ファイルへのデプロイにシリアル化しますすべてのアプリケーション アイテム 1 つのパッケージ。 これは、管理コンソールからエクスポート操作の手順を実行して、またはコマンドラインからの BTSTask.exe を使用して実行できます。 .Msi ファイルを作成したら、すべてを展開できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アセンブリには、BizTalk 管理グループのデータベースまたはインポート時に実行する指定されたスクリプトを実行します。 これは、Microsoft 管理コンソール (MMC) を使用して、.msi ファイルの (または BTSTASK コマンドラインからのインポート操作を使用して)、インポート操作を実行します。 .Msi ファイルのインポート操作では、展開先 BizTalk アプリケーションを作成します。  
  
 .Msi ファイルをすべての BizTalk Server アセンブリと依存関係アセンブリがコンピューターのグローバル アセンブリ キャッシュに格納されているように、1 台のコンピューター上のアプリケーションをデプロイできます。 コンピューターでは、すべての実行時に必要なバイナリしにします。 この操作の場合でも、ソリューションの一部である Web サービスを展開または、スクリプトでコンピューター固有の変更を適用できます。 この操作を実行するには、.msi ファイルを実行します。 関連する BizTalk グループのメンバーである BizTalk Server を実行している各コンピューターでこの操作を行うことができます。 グループに追加した新しいサーバーにアプリケーションをインストールするのに .msi ファイルを使用することもできます。  
  
 新しいグループを BizTalk アプリケーションを移行する場合は、新しいグループのすべてのサーバーで .msi のインストールを実行する必要があります。 グループに対して 1 回の .msi ファイルをインポートする必要があります。 操作を実行すると、新しいグループのすべての実行時のコンピューターにインストールされて、アプリケーションとその内容と、グループの BizTalk 管理データベースに登録されてです。 暗黙的なバインドだけでなく、.msi ファイルに複数のバインド ファイルを追加することもできます。 各追加のバインド ファイル「環境」と関連付けることができます。 複数のバインド ファイルが、デプロイ時に、BizTalk アプリケーションで関連しているときに、デプロイは、(運用環境、ステージング、またはテスト) 環境に基づいて、使用されるバインド ファイルを選択できます。  
  
 .Msi ファイルをスクリプトを使用して、サーバー (インストールの操作) またはグループ (インポートの操作) をカスタマイズすることができます。 .Msi ファイルでスクリプトの使用に関する詳細については、次を参照してください。[アプリケーション展開のカスタマイズを前処理および後処理のスクリプトを使用して](http://go.microsoft.com/fwlink/?LinkId=154995)(http://go.microsoft.com/fwlink/?LinkId=154995)します。  
  
 アプリケーションを展開する手順のチェックリストについては、次を参照してください。[チェックリスト。アプリケーションを展開する](../technical-guides/checklist-deploying-an-application.md)します。  
  
## <a name="exporting-an-applications-bindings-by-using-a-binding-file"></a>バインド ファイルを使用して、アプリケーションのバインドのエクスポート  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、バインド ファイルでは、アプリケーションのバインドをエクスポートし、バインド ファイルから別のアプリケーションにこれらのバインドをインポートします。 これを行うには、コピー先のアプリケーションは既に存在する必要があります。インポートの手順では、アプリケーションは作成されません。 バインド ファイルは、アプリケーション、グループ、またはアセンブリ内のすべての成果物のバインディングを含む XML ファイルです。 BizTalk グループのすべてのバインドまたは BizTalk アセンブリのバインドをエクスポートすることもできます。 バインドと操作の詳細については、次を参照してください。[バインド ファイルにバインドのエクスポート方法](../technical-guides/how-to-export-bindings-to-a-binding-file.md)と[バインド ファイルからバインドのインポート方法](../technical-guides/how-to-import-bindings-from-a-binding-file.md)します。  
  
 .Msi ファイルにリソースとしてバインド ファイルを追加することもできます。 リソースとしてバインド ファイルを追加する方法の詳細については、次を参照してください。[アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)します。  
  
 アプリケーションの展開の詳細については一般に、表示[Understanding BizTalk アプリケーションの展開と管理](http://go.microsoft.com/fwlink/?LinkId=154996)(http://go.microsoft.com/fwlink/?LinkId=154996)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アプリケーション展開のベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)  
  
-   [アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)  
  
-   [アプリケーションを管理するためのアクセス許可](../technical-guides/permissions-for-managing-an-application.md)  
  
-   [アプリケーション内で一意である必要があるアイテム](../technical-guides/artifacts-that-must-be-unique-in-an-application.md)  
  
-   [アプリケーションの展開とエクスポート](../technical-guides/deploying-and-exporting-an-application.md)