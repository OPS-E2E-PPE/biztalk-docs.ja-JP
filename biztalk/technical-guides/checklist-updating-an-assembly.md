---
title: チェックリスト:アセンブリの更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5afcb78a-333b-46ff-8681-42362ce5aaad
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84cf2efe1d1115ed4b7c8ab50692db6f8d430482
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242549"
---
# <a name="checklist-updating-an-assembly"></a>チェックリスト:アセンブリの更新
次のチェックリストでは、既にデプロイされているアプリケーションで 1 つまたは複数のアイテムを更新し、再度、アプリケーションをデプロイするプロセスについて説明します。  
  
> [!NOTE]  
>  ダウンタイムのスケジュールを設定するか、または終了することはできません非常に時間の長い実行インスタンスがあることはできない場合、は、サイド バイ サイド バージョン管理を使用して更新します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|アプリケーションでアイテムを更新するための重要な考慮事項を確認します。|-   [アプリケーションを更新するための重要な考慮事項](http://go.microsoft.com/fwlink/?LinkId=154823)(http://go.microsoft.com/fwlink/?LinkId=154823)します。<br />-   [アプリケーションの更新のベスト プラクティス](../technical-guides/best-practices-for-updating-applications.md)|  
|配置を実行する適切なアクセス許可があることを確認します。|[アプリケーションを管理するためのアクセス許可](../technical-guides/permissions-for-managing-an-application.md)|  
|アセンブリ、追加、削除、または必要に応じてアイテムを再構成するために必要な変更を加えます。<br /><br /> Visual Studio からアセンブリを開発環境で BizTalk アプリケーションに展開します。|-   [アセンブリを更新する方法](../technical-guides/how-to-update-an-assembly.md)<br />-   [アイテムの更新](../technical-guides/updating-an-artifact.md)<br />-「アイテムの更新」と"アセンブリの更新 のセクションでは[アプリケーションの更新のベスト プラクティス](../technical-guides/best-practices-for-updating-applications.md)<br />-   [Visual Studio から BizTalk アセンブリを展開する方法](http://go.microsoft.com/fwlink/?LinkId=154824)(http://go.microsoft.com/fwlink/?LinkId=154824)します。|  
|新規または変更された成果物に依存するすべてのアイテムもテストすることを確認、新しいまたは変更されたアイテムをテストします。 **注:** をテストする場合は、このアプリケーションとその他のアプリケーション間に存在する依存関係を考慮します。|[BizTalk アプリケーション展開のテスト作業](http://go.microsoft.com/fwlink/?LinkId=154825)(http://go.microsoft.com/fwlink/?LinkId=154825)します。|  
|BizTalk Server 管理コンソールで追加、削除、または必要に応じて、アプリケーション内のアイテムを再構成します。|-   [成果物を追加または作成する方法](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)します。<br />-   [アプリケーションからアイテムを削除する方法](http://go.microsoft.com/fwlink/?LinkID=154688)(http://go.microsoft.com/fwlink/?LinkID=154688)します。<br />-   [アイテムの管理](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)します。<br />-   [アイテムの更新](../technical-guides/updating-an-artifact.md)<br />-「アイテムの更新」のセクションの[アプリケーションの更新のベスト プラクティス](../technical-guides/best-practices-for-updating-applications.md)します。|  
|.Msi ファイルに追加または変更された成果物を含むアプリケーションをエクスポートします。|-   [BizTalk アプリケーション、バインド、およびポリシーのエクスポート](http://go.microsoft.com/fwlink/?LinkId=154826)(http://go.microsoft.com/fwlink/?LinkId=154826)します。<br />-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-「BizTalk アプリケーションをエクスポートする」のセクションの[アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)します。|  
|実行時に、更新プログラムは、アプリケーションを妨げる、ダウンタイム、スケジュールを設定し、更新するアプリケーションを停止します。|-   [BizTalk アプリケーション開始および停止方法](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)します。<br />-「を開始またはアプリケーションを停止しています」のセクションの[アプリケーションの更新のベスト プラクティス](../technical-guides/best-practices-for-updating-applications.md)します。|  
|.Msi ファイルから、アプリケーションのインストール、更新するアプリケーションに変更または更新したアイテムをインポートします。 **注:** BizTalk アセンブリを更新するときに停止して、.msi ファイルからインポートする前に成果物を参加解除する必要があります。 再参加して、.msi からインポートした後、BizTalk アイテムを起動する必要があります。|-   [BizTalk アプリケーションをインポートする方法](http://go.microsoft.com/fwlink/?LinkId=154827)(http://go.microsoft.com/fwlink/?LinkId=154827)します。<br />-   [アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-「BizTalk アプリケーションをインポートする」のセクションの[アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)します。<br />-   [BizTalk アプリケーションをインストールする方法](http://go.microsoft.com/fwlink/?LinkID=154728)(http://go.microsoft.com/fwlink/?LinkID=154728)します。<br />-   [アセンブリを GAC にインストールする方法](http://go.microsoft.com/fwlink/?LinkId=154828)(http://go.microsoft.com/fwlink/?LinkId=154828)します。|  
|メッセージの公開を再開する、アプリケーションを起動します。 すべての BizTalk ホスト インスタンスを再起動します。|-   [BizTalk アプリケーション開始および停止方法](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)します。|  
|オーケストレーションを含むアセンブリをインポートした後、停止をインポートする、既にアプリケーションに同じ名前、公開キー トークン、およびバージョンを持つアセンブリが含まれている場合と、オーケストレーションをホストのホスト インスタンスを開始します。バインドされています。 これにより、BizTalk Server によって、アセンブリの新しいバージョンを使用します。|-   [ホスト インスタンスを停止する方法](http://go.microsoft.com/fwlink/?LinkId=154829)(http://go.microsoft.com/fwlink/?LinkId=154829)します。<br />-   [ホスト インスタンスを開始する方法](http://go.microsoft.com/fwlink/?LinkId=154830)(http://go.microsoft.com/fwlink/?LinkId=154830)します。|