---
title: チェックリスト:アプリケーションの配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5e699ac3-7998-48d6-96b7-2f8f1a3d52e5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a66c63237e09431ce1a9e8c711551e411ea20e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401823"
---
# <a name="checklist-deploying-an-application"></a>チェックリスト:アプリケーションを展開します。
このトピックでは、BizTalk アプリケーションと、運用環境では、そのアイテムを展開する手順について説明します。 開発環境でアプリケーションを展開し、.msi ファイルにエクスポート、.msi ファイルから運用環境にインポートする方法を示します。  
  
 アプリケーションの展開は、グループにアプリケーションをインポートして、グループ内の個々 のサーバー (ホスト インスタンス) で、アプリケーションのインストールで構成されます。 インポートして、アプリケーションのインストールの詳細については、次を参照してください。[アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)します。  
  
 アプリケーションの展開の詳細については、次を参照してください。 [、アプリケーションの展開プロセス](http://go.microsoft.com/fwlink/p/?LinkId=154716)(http://go.microsoft.com/fwlink/p/?LinkId=154716)します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|配置を実行する適切なアクセス許可があることを確認します。|[アプリケーションを管理するためのアクセス許可](../technical-guides/permissions-for-managing-an-application.md)|  
|Visual Studio でアセンブリに展開されるアプリケーションなど、BizTalk Server ソリューション内の各プロジェクトの配置プロパティを設定します。<br /><br /> 開発環境で BizTalk アプリケーションに必要な BizTalk Server アセンブリを展開 (または再デプロイ)。|-   [Visual Studio での展開のプロパティを設定する方法](http://go.microsoft.com/fwlink/p/?LinkId=154718)(http://go.microsoft.com/fwlink/p/?LinkId=154718)します。<br />-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開](http://go.microsoft.com/fwlink/p/?LinkId=154719)(http://go.microsoft.com/fwlink/p/?LinkId=154719)します。<br />-   [Visual Studio から BizTalk アセンブリを再デプロイする方法](http://go.microsoft.com/fwlink/p/?LinkId=154720)(http://go.microsoft.com/fwlink/p/?LinkId=154720)します。<br />-   [アセンブリを展開します。](../technical-guides/deploying-an-assembly.md)<br />-「BizTalk アプリケーション展開」、「BizTalk アプリケーションを作成する」および「BizTalk アセンブリを展開する」のセクションでは[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)します。<br />-「BizTalk アプリケーションを展開する」のセクションの[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)します。|  
|BizTalk アプリケーションにアイテムを追加し、開発環境で、成果物を構成します。<br /><br /> これは、成果物を複数の BizTalk アプリケーションにファクタリングを含めることができます。|-   [成果物を追加または作成する方法](http://go.microsoft.com/fwlink/p/?LinkId=154724)(http://go.microsoft.com/fwlink/p/?LinkId=154724)します。<br />-   [アイテムの管理](http://go.microsoft.com/fwlink/p/?LinkId=154725)(http://go.microsoft.com/fwlink/p/?LinkId=154725)します。<br />-   [バインド ファイルとアプリケーションの展開](http://go.microsoft.com/fwlink/p/?LinkId=154726)(http://go.microsoft.com/fwlink/p/?LinkId=154726)します。<br />-   [成果物をアプリケーションに追加します。](../technical-guides/adding-artifacts-to-an-application.md)<br />-「成果物を BizTalk アプリケーションに追加する」のセクションの[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)します。<br />-「成果物を BizTalk アプリケーションに追加する」のセクションの[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)します。|  
|開発環境で .msi ファイルに BizTalk アプリケーションをエクスポートします。|-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-「BizTalk アプリケーションをエクスポートする」のセクションの[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)します。<br />-「BizTalk アプリケーションをエクスポートする」のセクションの[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)します。|  
|BizTalk アプリケーションを .msi ファイルから実稼働環境にインポートします。 (この操作では、グループにアプリケーションをインポートし、アプリケーションには、ファイル ベースのアイテムが含まれている場合は、グループ内の各サーバーにアプリケーションをインストールします。)|-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [アプリケーションをインストールする方法](http://go.microsoft.com/fwlink/p/?LinkId=154728)(http://go.microsoft.com/fwlink/p/?LinkId=154728)します。<br />-「BizTalk アプリケーションをインポートする」のセクションの[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)<br />-「BizTalk アプリケーションをインポートする」のセクションの[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)|  
|ポート構成の変更など、その環境で実行されるように、運用環境で BizTalk アプリケーションに追加変更を加えます。 これを行う場合は、.msi ファイルにアプリケーションをエクスポートします。|-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [作成して、BizTalk アプリケーションを変更](http://go.microsoft.com/fwlink/p/?LinkId=154727)(http://go.microsoft.com/fwlink/p/?LinkId=154727)します。<br />-   [バインド ファイルを Application1 を追加する方法](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)<br />-「BizTalk アプリケーションをエクスポートする」のセクションの[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)<br />-「BizTalk アプリケーションをエクスポートする」のセクションの[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)|  
|運用環境で BizTalk アプリケーションに、追加の変更を加えた場合 .msi ファイルから BizTalk アプリケーションの他のコンピューターで実行する運用環境にインストールします。<br /><br /> それを配置する他の BizTalk グループにアプリケーションをインポートし、アプリケーションには、ファイル ベースのアイテムが含まれている場合は、それらのグループ内のサーバーでアプリケーションをインストールします。|-   [BizTalk アプリケーションをインストールする方法](http://go.microsoft.com/fwlink/p/?LinkId=154728)(http://go.microsoft.com/fwlink/p/?LinkId=154728)します。<br />-   [アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-「BizTalk アプリケーションをインポートする」のセクションの[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)<br />-「BizTalk アプリケーションをインポートする」のセクションの[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)|  
|BizTalk Server 管理コンソールから運用環境で BizTalk アプリケーションを起動し、正しく機能していることを確認します。|-   [BizTalk アプリケーション開始および停止方法](http://go.microsoft.com/fwlink/p/?LinkId=154729)(http://go.microsoft.com/fwlink/p/?LinkId=154729)します。<br />-   [アプリケーションのテスト](../technical-guides/testing-an-application.md)|  
  
## <a name="see-also"></a>参照  
 [アセンブリを展開します。](../technical-guides/deploying-an-assembly.md)   
 [成果物をアプリケーションに追加します。](../technical-guides/adding-artifacts-to-an-application.md)   
 [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)   
 [バインド ファイルにバインドをエクスポートする方法](../technical-guides/how-to-export-bindings-to-a-binding-file.md)   
 [アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)   
 [アプリケーションをインストールする方法](../technical-guides/how-to-install-an-application.md)   
 [バインド ファイルからバインドをインポートする方法](../technical-guides/how-to-import-bindings-from-a-binding-file.md)