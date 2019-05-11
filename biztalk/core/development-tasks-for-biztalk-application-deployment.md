---
title: BizTalk アプリケーション展開の開発タスク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, deploying
- deploying [applications], developing
- applications, tasks
- deploying [applications], warnings
- applications, developing
- developing, tasks
ms.assetid: b441d4f4-122e-4caf-8381-723c6142b0b6
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b935f2aee0687a12c7b4519b2f44abf90a75e8e
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530868"
---
# <a name="development-tasks-for-biztalk-application-deployment"></a>BizTalk アプリケーション展開の開発作業
[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] から BizTalk アプリケーションに BizTalk アセンブリを展開し、アプリケーションを完成させて、テスト環境に展開できるようにアプリケーションを準備するための手順を次に示します。 この展開シナリオは、プログラマが特定の BizTalk ビジネス ソリューションの開発およびデバッグを行う開発環境において一般的なものです。  
  
> [!IMPORTANT]
>  ここで説明する作業は、実稼働コンピューターでは行わないでください。 開発の過程ではしばしば、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からのアセンブリの再展開が必要になります。 再展開を可能にするため、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] では同じまたは別のアプリケーション内に存在するアセンブリの展開解除、バインド解除、停止、および参加解除が行われます。 これは開発環境では必要であり適切なことですが、実稼働環境では予期しない結果や結果や好ましくない結果を引き起こす可能性があります。 また、実稼働コンピューター上の [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からアセンブリが展開される危険性を回避するために、実稼働コンピューターには [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] をインストールしないことをお勧めします。  
  
1. **開発し、BizTalk アセンブリをビルドします。** BizTalk ビジネス ソリューションを作成することから始める[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]オーケストレーション、スキーマ、マップ、およびパイプラインを使用します。 ソリューションを作成する際には、1 つまたは複数の BizTalk アセンブリ内でソリューションをビルドします。 詳細については、次を参照してください。 [BizTalk Server アプリケーションの開発](../core/developing-biztalk-server-applications.md)します。 また、ソリューションが機能するために必要な BizTalk 以外の .NET アセンブリも開発およびビルドします。  
  
2. **展開のプロパティを設定します。** 各展開のプロパティを設定する BizTalk アセンブリを展開する準備ができたら、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューション内のプロジェクト。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の各プロパティ ("サーバー"、"構成"、"データベース"、"再展開"、"ホスト インスタンスを再起動します"、"グローバル アセンブリ キャッシュにインストール") に加えて、"アプリケーション名" プロパティも設定できます。 このプロパティでは、各アセンブリを展開する BizTalk アプリケーションを指定します。 "アプリケーション名" が空白の場合、アセンブリは既定のアプリケーションに展開されます。 詳細については、次を参照してください。 [Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)します。 BizTalk 以外の .NET アセンブリを BizTalk アプリケーションに追加して展開する必要があります。 これは別の手順であり、手順 4. で説明します。  
  
3. **BizTalk Server がローカル コンピューター上で実行するには、BizTalk アセンブリを展開します。** 右クリックし、メニュー オプションから BizTalk アセンブリを展開することができます、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ソリューションと展開コマンドを選択します。 これにより、BizTalk アセンブリがソリューションのプロジェクト内でビルドされ、各プロジェクトの展開プロパティで定義した BizTalk アプリケーションに追加されます。 指定したアプリケーションが存在しない場合は、新しく作成されます。 "アイテム" と呼ばれるアセンブリおよびそのリソースは、グループの BizTalk 管理データベースにも展開され、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールやその他のツールを使用して表示および管理することができます。 この手順の詳細については、次を参照してください。 [Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)します。  
  
4. **アプリケーションが正しく機能するのに必要な成果物を追加します。** 内から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、アプリケーションを追加し、送信などの成果物を削除するなど、完了し、受信ポート、スクリプト、ポリシー、BizTalk 以外の .NET アセンブリなどを簡単に変更できます。 詳細については、次を参照してください。[を変更する BizTalk アプリケーションの作成と](../core/creating-and-modifying-biztalk-applications.md)します。  
  
5. **複数のアプリケーションには、成果物を考慮します。** 開発プロセス中に、利便性のためにアセンブリを単一のアプリケーションに展開することがあります。 さまざまな理由により、実稼働環境に展開する前にアセンブリを複数のアプリケーションにファクタリングする必要が生じる場合があります。 アプリケーションのファクタリングに関するベスト プラクティスの詳細については、次を参照してください。 [BizTalk アプリケーションの展開のベスト プラクティス](../core/best-practices-for-deploying-a-biztalk-application.md)します。  
  
6. **ソリューション内のすべてのアプリケーションの .msi ファイルを作成し、ローカルにインストールします。** 使用可能なエクスポート ウィザードを使用することができますか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールまたは BTSTask コマンド ライン ツールは、各アプリケーションのアイテムを含む .msi ファイルを作成します。 詳細については、次を参照してください。 [BizTalk アプリケーションのエクスポート、バインド、およびポリシー](../core/exporting-biztalk-applications-bindings-and-policies.md)します。 ソリューションをローカル コンピューターで実行し、ソリューションが予想どおりに機能していることを確認する場合は、.msi ファイルからアイテムをインストールするための追加手順を実行できます。 詳細については、次を参照してください。 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。 ソリューションが予想どおりに機能することを確認します。  
  
7. **必要に応じて、BizTalk アセンブリを再デプロイします。** 開発し、BizTalk アセンブリのデバッグを処理中には、複数回再配置する必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 再デプロイする簡単なメカニズムを提供します。 詳細については、次を参照してください。 [Visual Studio から BizTalk アセンブリを再デプロイする方法](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)します。  
  
8. **バインド ファイルをエクスポートし、(省略可能) のアプリケーションに再度追加します。** 変更または追加を行うためにアプリケーションを開発環境に後で簡単に再インポートできるようにするには、各アプリケーションのバインドをエクスポートし、バインドの対象となる開発環境を指定してアプリケーションに再度追加します。 アプリケーションの .msi ファイルを開発コンピューターの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に後で再インポートするときに、これらのバインドを適用するように指定できます。 詳細については、次を参照してください。[バインド ファイルとアプリケーションの展開](../core/binding-files-and-application-deployment.md)します。  
  
9. **テスト チームを渡すために各アプリケーションの .msi ファイルを生成**します。 開発と、BizTalk ソリューションのデバッグが完了したらは、手順 6 で前述したように、アプリケーションの .msi ファイルを生成するのにエクスポート ウィザードまたは BTSTask に使用できます。 別の BizTalk グループに、開発環境でこれらのファイルをインポートする必要があります、それをインストールし、ソリューションが期待どおりに機能していることを確認します。 渡すことができますし、テスト チームに使用できるアプリケーションをインポートする .msi ファイルの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]」の説明に従って、テスト コンピューターでも、それらをインストールしたり実行[BizTalk アプリケーション展開のテストタスク](../core/testing-tasks-for-biztalk-application-deployment.md).  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開作業](../core/application-deployment-tasks.md)