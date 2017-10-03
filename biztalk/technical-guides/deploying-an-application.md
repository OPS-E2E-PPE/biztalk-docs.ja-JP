---
title: "アプリケーションを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04bb4496-b1e9-400b-a849-a355381849ff
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61bc0e446e635fd4111804f7160651df6492a60c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-an-application"></a>アプリケーションを展開します。
展開は、ロジスティック分布のすべての必要なコンポーネントを必要とするシステムに使用できるようにするアプリケーションのアイテムです。 これらの成果物には、BizTalk Server アセンブリ、.NET アセンブリ、スキーマ、マップ、バインド、ビジネス ルール、および証明書が含まれます。 BizTalk アプリケーションを利用して他のコンピューター (別の環境にアプリケーションを転送) するときに、グループまたはステージングのために追加する成果物のロールアウトを支援します。  
  
 たとえば、アプリケーションの一部として、それらをインポートする (.msi ファイルから)、配置ウィザードを使用して BTSTask.exe を使用して、インポート、Visual Studio から配置するまたは MSBuild を使用して BizTalk アイテムを配置するさまざまな方法があります。 インポートするには場合 BTSTask.exe を使用して、それらを展開または、Visual Studio から、それらを展開するアプリケーションを指定するか空白のままにアプリケーション名に展開する場合は、既定のアプリケーションにします。  
  
## <a name="deploying-by-using-an-msi-file"></a>.Msi ファイルを使用して展開します。  
 BizTalk Server では、.msi ファイルにエクスポートして、アプリケーションとそのアイテムを展開できます。 (アプリケーションとアイテムの詳細については、次を参照してください。 [BizTalk アプリケーションは何ですか。](http://go.microsoft.com/fwlink/?LinkId=154994) (http://go.microsoft.com/fwlink/?LinkId=154994)。 BizTalk アプリケーションの展開には、アプリケーションのアイテムを BizTalk 管理データベースにインポートするだけでなく、グループのメンバーである各コンピューターに、成果物のインストールが含まれます。 .Msi ファイルへの展開にシリアル化アプリケーションのすべてのアイテム 1 つのパッケージです。 これは、管理コンソールからエクスポート操作の手順を実行して、またはコマンドラインからの BTSTask.exe を使用して実行できます。 .Msi ファイルを作成したら、すべてを展開できます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アセンブリには、BizTalk 管理グループのデータベースまたはインポート時に実行する指定されたスクリプトを実行します。 これは、Microsoft 管理コンソール (MMC) を使用し、(または BTSTASK コマンド ラインからのインポート操作を使用して)、.msi ファイルのインポート操作を行う方法を実行します。 .Msi ファイルのインポート操作では、移行先の BizTalk アプリケーションを作成します。  
  
 .Msi ファイルをすべての BizTalk Server アセンブリと依存アセンブリがコンピューターのグローバル アセンブリ キャッシュに格納されているように、1 台のコンピューター上のアプリケーションを展開できます。 コンピューターでは、すべての実行時に必要なバイナリしにします。 この操作でも、このソリューションの一部である Web サービスを展開したり、スクリプトによってコンピューターに固有の変更を適用できます。 この操作を実行するには、.msi ファイルを実行します。 関連する BizTalk グループのメンバーである BizTalk Server を実行する各コンピューターでこの操作を行うことができます。 グループに追加された新しいサーバーにアプリケーションをインストールするのに .msi ファイルを使用することもできます。  
  
 新しいグループに、BizTalk アプリケーションを移行する場合は、新しいグループ内のすべてのサーバーで、.msi インストールを実行する必要があります。 グループの 1 回の .msi ファイルをインポートする必要があります。 操作を実行すると、新しいグループ内のすべてのランタイム コンピューターにインストールされてアプリケーションとその内容と、グループの BizTalk 管理データベースにも登録されています。 暗黙のバインドだけでなく、.msi ファイルに複数のバインド ファイルを追加することもできます。 各追加のバインド ファイルは、「環境」に関連付けることができます。 複数のバインド ファイルが、配置時に BizTalk アプリケーションに関連付けられている場合にを展開する (実稼働環境、ステージング、またはテスト) 環境に基づいて、使用されるバインド ファイルを選択できます。  
  
 .Msi ファイルにスクリプトを使用して、サーバー (インストールの操作) またはグループ (インポート操作) をカスタマイズすることができます。 詳細については、.msi ファイルにスクリプトを使用して、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](http://go.microsoft.com/fwlink/?LinkId=154995)(http://go.microsoft.com/fwlink/?LinkId=154995)。  
  
 アプリケーションを展開するための手順のチェックリストについては、次を参照してください。[チェックリスト: アプリケーションを配置する](../technical-guides/checklist-deploying-an-application.md)です。  
  
## <a name="exporting-an-applications-bindings-by-using-a-binding-file"></a>バインド ファイルを使用して、アプリケーションのバインドのエクスポート  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、バインド ファイルにアプリケーションのバインドをエクスポートし、バインド ファイルから別のアプリケーションにこれらのバインドをインポートします。 これを行うには、コピー先のアプリケーションが既に存在してます。インポート手順では、アプリケーションは作成されません。 バインド ファイルとは、アプリケーション、グループ、またはアセンブリ内のすべての成果物のバインディングを含む XML ファイルです。 BizTalk グループのすべてのバインディングまたは BizTalk アセンブリのバインドをエクスポートすることもできます。 バインディングの使用の詳細については、次を参照してください。[をバインド ファイルのバインドのエクスポート方法](../technical-guides/how-to-export-bindings-to-a-binding-file.md)と[バインド ファイルからバインドのインポート方法](../technical-guides/how-to-import-bindings-from-a-binding-file.md)です。  
  
 .Msi ファイルにリソースとしてバインド ファイルを追加することもできます。 リソースとしてバインド ファイルを追加する方法の詳細については、次を参照してください。[アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)です。  
  
 アプリケーションの展開の詳細については一般を参照してください[Understanding BizTalk アプリケーションの展開と管理](http://go.microsoft.com/fwlink/?LinkId=154996)(http://go.microsoft.com/fwlink/?LinkId=154996)。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)  
  
-   [アプリケーションの配置に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)  
  
-   [アプリケーションを管理するためのアクセス許可](../technical-guides/permissions-for-managing-an-application.md)  
  
-   [成果物をアプリケーション内で一意である必要があります。](../technical-guides/artifacts-that-must-be-unique-in-an-application.md)  
  
-   [展開して、アプリケーションをエクスポートします。](../technical-guides/deploying-and-exporting-an-application.md)