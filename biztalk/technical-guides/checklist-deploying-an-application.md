---
title: "チェックリスト: アプリケーションを展開する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e699ac3-7998-48d6-96b7-2f8f1a3d52e5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 713eef12a06cb8331faf39acede7c14143a45032
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-deploying-an-application"></a>チェックリスト: アプリケーションを展開します。
このトピックでは、BizTalk アプリケーションと、運用環境でそのアイテムを展開する手順について説明します。 開発環境でアプリケーションを展開、.msi ファイルにエクスポートし、.msi ファイルから実稼働環境にインポートする方法を示します。  
  
 アプリケーションの展開は、グループにアプリケーションをインポートして、グループ内の個々 のサーバー (ホスト インスタンス) でアプリケーションをインストールするので構成されます。 インポートして、アプリケーションのインストールに関する詳細については、次を参照してください。 [.msi ファイルからアプリケーションをインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)です。  
  
 アプリケーションの展開の詳細については、次を参照してください。 [、アプリケーションの展開プロセス](http://go.microsoft.com/fwlink/p/?LinkId=154716)(http://go.microsoft.com/fwlink/p/?LinkId=154716)。  
  
|手順|リファレンス|  
|-----------|---------------|  
|配置を実行する適切なアクセス許可があることを確認します。|[アプリケーションを管理するためのアクセス許可](../technical-guides/permissions-for-managing-an-application.md)|  
|各プロジェクトにアセンブリが展開されるアプリケーションなど、BizTalk Server ソリューションでの Visual Studio で、展開のプロパティを設定します。<br /><br /> 開発環境で BizTalk アプリケーションに必要な BizTalk Server アセンブリを展開 (または再配置) します。|-   [Visual Studio での展開のプロパティを設定する方法](http://go.microsoft.com/fwlink/p/?LinkId=154718)(http://go.microsoft.com/fwlink/p/?LinkId=154718)。<br />-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/p/?LinkId=154719)(http://go.microsoft.com/fwlink/p/?LinkId=154719)。<br />-   [Visual Studio から BizTalk アセンブリを再展開する方法](http://go.microsoft.com/fwlink/p/?LinkId=154720)(http://go.microsoft.com/fwlink/p/?LinkId=154720)。<br />-   [アセンブリを展開します。](../technical-guides/deploying-an-assembly.md)<br />-「BizTalk アプリケーション展開」、「BizTalk アプリケーションを作成する」および「BizTalk アセンブリを展開する」のセクション[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)です。<br />「BizTalk アプリケーションを展開する」セクション[に関する既知の問題をアプリケーションを配置する](../technical-guides/known-issues-with-deploying-an-application.md)です。|  
|BizTalk アプリケーションにアイテムを追加し、開発環境でのアイテムを構成します。<br /><br /> これは、成果物の複数の BizTalk アプリケーションにファクタリングを含めることができます。|-   [成果物を追加または作成する方法](http://go.microsoft.com/fwlink/p/?LinkId=154724)(http://go.microsoft.com/fwlink/p/?LinkId=154724)。<br />-   [成果物の管理](http://go.microsoft.com/fwlink/p/?LinkId=154725)(http://go.microsoft.com/fwlink/p/?LinkId=154725)。<br />-   [バインド ファイルとアプリケーションの配置](http://go.microsoft.com/fwlink/p/?LinkId=154726)(http://go.microsoft.com/fwlink/p/?LinkId=154726)。<br />-   [成果物をアプリケーションに追加します。](../technical-guides/adding-artifacts-to-an-application.md)<br />-のセクションの「アイテムを BizTalk アプリケーションを追加」[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)です。<br />-のセクションの「アイテムを BizTalk アプリケーションを追加」[に関する既知の問題をアプリケーションを配置する](../technical-guides/known-issues-with-deploying-an-application.md)です。|  
|BizTalk アプリケーションを開発環境で .msi ファイルにエクスポートします。|-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-のセクションの「BizTalk アプリケーションをエクスポートする」[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)です。<br />-のセクションの「BizTalk アプリケーションをエクスポートする」[に関する既知の問題をアプリケーションを配置する](../technical-guides/known-issues-with-deploying-an-application.md)です。|  
|BizTalk アプリケーションを .msi ファイルから実稼働環境にインポートします。 (この操作では、グループにアプリケーションをインポートして、アプリケーションには、ファイル ベースのアイテムが含まれている場合は、グループ内の各サーバーにアプリケーションをインストールします。)|-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [アプリケーションをインストールする方法](http://go.microsoft.com/fwlink/p/?LinkId=154728)(http://go.microsoft.com/fwlink/p/?LinkId=154728)。<br />-のセクションの「BizTalk アプリケーションのインポート」[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)<br />-のセクションの「BizTalk アプリケーションのインポート」[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)|  
|ポート構成の変更など、その環境で実行されるように、実稼働環境で BizTalk アプリケーションに追加変更を加えます。 これを行う場合は、.msi ファイルにアプリケーションをエクスポートします。|-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [作成して、BizTalk アプリケーションを変更する](http://go.microsoft.com/fwlink/p/?LinkId=154727)(http://go.microsoft.com/fwlink/p/?LinkId=154727)。<br />-   [バインド ファイルをアプリケーション 1 に追加する方法](../technical-guides/how-to-add-a-binding-file-to-an-application1.md)<br />-のセクションの「BizTalk アプリケーションをエクスポートする」[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)<br />-のセクションの「BizTalk アプリケーションをエクスポートする」[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)|  
|実稼働環境で BizTalk アプリケーションに、追加の変更を加えた場合は、それを実行する実稼働環境でその他のコンピューターに、.msi ファイルから BizTalk アプリケーションをインストールします。<br /><br /> またがそれを配置する他の BizTalk グループにアプリケーションをインポートし、アプリケーションには、ファイル ベースのアイテムが含まれている場合は、それらのグループ内のサーバーにアプリケーションをインストールします。|-   [BizTalk アプリケーションをインストールする方法](http://go.microsoft.com/fwlink/p/?LinkId=154728)(http://go.microsoft.com/fwlink/p/?LinkId=154728)。<br />-   [アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-のセクションの「BizTalk アプリケーションのインポート」[アプリケーションを展開するためのベスト プラクティス](http://msdn.microsoft.com/library/gg634504.aspx)<br />-のセクションの「BizTalk アプリケーションのインポート」[アプリケーションの展開に関する既知の問題](../technical-guides/known-issues-with-deploying-an-application.md)|  
|BizTalk Server 管理コンソールから実稼働環境で BizTalk アプリケーションを起動し、正しく機能していることを確認します。|-   [BizTalk アプリケーション開始および停止する方法](http://go.microsoft.com/fwlink/p/?LinkId=154729)(http://go.microsoft.com/fwlink/p/?LinkId=154729)。<br />-   [アプリケーションのテスト](../technical-guides/testing-an-application.md)|  
  
## <a name="see-also"></a>参照  
 [アセンブリを展開します。](../technical-guides/deploying-an-assembly.md)   
 [成果物をアプリケーションに追加します。](../technical-guides/adding-artifacts-to-an-application.md)   
 [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)   
 [バインドをバインド ファイルにエクスポートする方法](../technical-guides/how-to-export-bindings-to-a-binding-file.md)   
 [アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)   
 [アプリケーションをインストールする方法](../technical-guides/how-to-install-an-application.md)   
 [バインド ファイルからバインドをインポートする方法](../technical-guides/how-to-import-bindings-from-a-binding-file.md)