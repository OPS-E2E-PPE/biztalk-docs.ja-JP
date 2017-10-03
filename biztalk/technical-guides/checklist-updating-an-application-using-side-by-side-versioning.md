---
title: "チェックリスト: サイド バイ サイドのバージョン管理を使用してアプリケーションの更新 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3adee8da-18d4-4b9e-a22e-148b90d18179
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5447743ff9cdc7a109d78c3dac57e0e3345556a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-updating-an-application-using-side-by-side-versioning"></a>チェックリスト: サイド バイ サイドのバージョン管理を使用してアプリケーションの更新
次のチェックリストは、サイド バイ サイドを実行する BizTalk アプリケーションの更新バージョンを展開するプロセスを説明します。 既存のバージョン。  
  
 サイド バイ サイド インストールでは、アプリケーションのアップグレードを段階的ロールアウトすることができます。 インストールが使用できるようにビジネス パートナーのサブセットにすべてのパートナーではなく、最初に、1 回にします。 このアプローチを使用するには、サービスはまだ使用していない新しいバージョン、新しいバージョンに完全に移動する準備ができるまで、ユーザーに既存のアプリケーションの実行を継続することができます。  
  
 2 つのサイド バイ サイドのアプリケーションが受信する必要が 2 つの異なるでメッセージの受信場所。 その結果、サイド バイ サイドのアプリケーションを実行する必要があります依頼するこれらの取引先アプリケーションの新しいバージョンを使用して、受信場所、新しいメッセージを送信する、新しいバージョンで処理するようにする必要があります。 前のメッセージの受信場所、取引先の古いバージョンを使用する必要があります送信する必要があります。  
  
|手順|リファレンス|  
|-----------|---------------|  
|作成し、バージョン管理の戦略を実装します。|「のバージョン管理」のセクションで[アプリケーションの更新に関するベスト プラクティス](../technical-guides/best-practices-for-updating-applications.md)です。|  
|プロジェクトを新しいバージョンのアプリケーションに展開するには、必要な変更を加えます。|-   [成果物を追加または作成する方法](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)。<br />-   [成果物の管理](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)。<br />-   [バインド ファイルとアプリケーションの配置](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)。<br />-   [成果物をアプリケーションに追加します。](../technical-guides/adding-artifacts-to-an-application.md)|  
|各アセンブリのバージョン番号をインクリメントします。|[アセンブリを更新する方法](../technical-guides/how-to-update-an-assembly.md)|  
|(コピー先のアプリケーションの設定とグローバル アセンブリ キャッシュ (GAC) にインストールを有効にする)、ソリューション内の各プロジェクトの配置プロパティを設定します。|[アセンブリを更新する方法](../technical-guides/how-to-update-an-assembly.md)|  
|開発環境でアプリケーションに変更されたアセンブリを含むソリューションを展開します。|-   [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](http://go.microsoft.com/fwlink/?LinkID=154719)(http://go.microsoft.com/fwlink/?LinkID=154719)。<br />-   [Visual Studio から BizTalk アセンブリを再展開する方法](http://go.microsoft.com/fwlink/?LinkID=154720)(http://go.microsoft.com/fwlink/?LinkID=154720)。<br />-   [アセンブリを展開します。](../technical-guides/deploying-an-assembly.md)|  
|新しい受信ポートと、いずれかに必要な受信パートナーにメッセージを送信する新しい Url を指定する場所です。<br /><br /> 必要に応じて、適切な送信ポートを作成します。<br /><br /> 必要に応じて、バインドを新しく作成された新しいアプリケーションが受信し、送信ポート、テスト アプリケーションが動作します。|-   [作成する方法、受信ポート](http://go.microsoft.com/fwlink/?LinkId=154843)(http://go.microsoft.com/fwlink/?LinkId=154843)。<br />-   [作成する方法、受信場所](http://go.microsoft.com/fwlink/?LinkId=154844)(http://go.microsoft.com/fwlink/?LinkId=154844)。<br />-   [送信ポートを作成する方法](http://go.microsoft.com/fwlink/?LinkId=154845)(http://go.microsoft.com/fwlink/?LinkId=154845)。<br />-   [アプリケーションを構成する方法](http://go.microsoft.com/fwlink/?LinkId=154847)(http://go.microsoft.com/fwlink/?LinkId=154847)。|  
|開発環境から .msi ファイルに新しいアプリケーションをエクスポートします。|-   [BizTalk アプリケーションのエクスポート方法](http://go.microsoft.com/fwlink/?LinkId=154848)(http://go.microsoft.com/fwlink/?LinkId=154848)。<br />-   [バインド ファイルとアプリケーションの配置](http://go.microsoft.com/fwlink/?LinkID=154726)(http://go.microsoft.com/fwlink/?LinkID=154726)。<br />-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [バインドをバインド ファイルにエクスポートする方法](../technical-guides/how-to-export-bindings-to-a-binding-file.md)|  
|運用環境で BizTalk グループには、アプリケーションの .msi ファイルをインポートします。|-   [BizTalk アプリケーションをインポートする方法](http://go.microsoft.com/fwlink/?LinkId=154827)(http://go.microsoft.com/fwlink/?LinkId=154827)。<br />-   [BizTalk アプリケーションをインストールする方法](http://go.microsoft.com/fwlink/?LinkID=154728)(http://go.microsoft.com/fwlink/?LinkID=154728)。<br />-   [アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-   [バインド ファイルからバインドをインポートする方法](../technical-guides/how-to-import-bindings-from-a-binding-file.md)|  
|アプリケーションが完全に開始を実行します。|-   [BizTalk アプリケーション開始および停止する方法](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)。<br />-   [BizTalk アプリケーションの展開のテスト作業](http://go.microsoft.com/fwlink/?LinkId=154825)(http://go.microsoft.com/fwlink/?LinkId=154825)。|  
|新しい Url へのメッセージ送信を開始する必要があります、パートナーに通知します。 パートナーがこれを実行すると、アプリケーションによって指定したパートナーに対するメッセージの処理が開始されます。|-|