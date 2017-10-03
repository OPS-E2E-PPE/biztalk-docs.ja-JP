---
title: "チェックリスト: アセンブリの更新 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5afcb78a-333b-46ff-8681-42362ce5aaad
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9b20aa7d1b0b901176f090ab7636ef0b3eccfa9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-updating-an-assembly"></a>チェックリスト: アセンブリを更新します。
次のチェックリストでは、既に配置されているアプリケーションで 1 つまたは複数のアイテムを更新し、アプリケーションを再配置し、プロセスについて説明します。  
  
> [!NOTE]  
>  ダウンタイムをスケジュールまたは終了できません非常に長時間のインスタンスがあることはできませんは、サイド バイ サイドのバージョン管理を使用して更新します。  
  
|手順|リファレンス|  
|-----------|---------------|  
|アプリケーションでアイテムを更新するための重要な考慮事項を確認します。|-   [アプリケーションを更新するための重要な考慮事項](http://go.microsoft.com/fwlink/?LinkId=154823)(http://go.microsoft.com/fwlink/?LinkId=154823)。<br />-   [アプリケーションの更新のベスト プラクティス](../technical-guides/best-practices-for-updating-applications.md)|  
|展開を実行するための適切なアクセス許可があることを確認します。|[アプリケーションを管理するためのアクセス許可](../technical-guides/permissions-for-managing-an-application.md)|  
|アセンブリの追加、削除、または必要に応じてアイテムを再構成するために必要な変更を加えます。<br /><br /> 開発環境で BizTalk アプリケーションに Visual Studio からアセンブリを展開します。|-   [アセンブリを更新する方法](../technical-guides/how-to-update-an-assembly.md)<br />-   [成果物の更新](../technical-guides/updating-an-artifact.md)<br />「アイテムの更新」と「アセンブリの更新」のセクション[アプリケーションの更新に関するベスト プラクティス](../technical-guides/best-practices-for-updating-applications.md)<br />-   [Visual Studio から BizTalk アセンブリを展開する方法](http://go.microsoft.com/fwlink/?LinkId=154824)(http://go.microsoft.com/fwlink/?LinkId=154824)。|  
|新しいアイテムまたは変更されたアイテムをテストします。新しいアイテムまたは変更されたアイテムに依存する可能性があるすべてのアイテムもテストします。 **注:**をテストするときは必ずこのアプリケーションとその他のアプリケーション間に存在する依存関係を考慮します。|[BizTalk アプリケーションの展開のテスト作業](http://go.microsoft.com/fwlink/?LinkId=154825)(http://go.microsoft.com/fwlink/?LinkId=154825)。|  
|BizTalk Server 管理コンソールで、追加、削除、または必要に応じて、アプリケーション内のアイテムを再構成します。|-   [成果物を追加または作成する方法](http://go.microsoft.com/fwlink/?LinkID=154724)(http://go.microsoft.com/fwlink/?LinkID=154724)。<br />-   [アプリケーションからアイテムを削除する方法](http://go.microsoft.com/fwlink/?LinkID=154688)(http://go.microsoft.com/fwlink/?LinkID=154688)。<br />-   [成果物の管理](http://go.microsoft.com/fwlink/?LinkID=154725)(http://go.microsoft.com/fwlink/?LinkID=154725)。<br />-   [成果物の更新](../technical-guides/updating-an-artifact.md)<br />-のセクションの「アイテムの更新」[アプリケーションの更新に関するベスト プラクティス](../technical-guides/best-practices-for-updating-applications.md)です。|  
|新しいアイテムや変更されたアイテムを含むアプリケーションを .msi ファイルにエクスポートします。|-   [BizTalk アプリケーション、バインド、およびポリシーをエクスポートする](http://go.microsoft.com/fwlink/?LinkId=154826)(http://go.microsoft.com/fwlink/?LinkId=154826)。<br />-   [アプリケーションを .msi ファイルにエクスポートする方法](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-のセクションの「BizTalk アプリケーションをエクスポートする」[アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)です。|  
|更新プログラムは、実行時に、アプリケーションが妨げられます場合、ダウンタイムをスケジュールし、更新するアプリケーションを停止します。|-   [BizTalk アプリケーション開始および停止する方法](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)。<br />-「を開始またはアプリケーションの停止」のセクションの[アプリケーションの更新に関するベスト プラクティス](../technical-guides/best-practices-for-updating-applications.md)です。|  
|.Msi ファイルから、アプリケーションのインストール、更新する、アプリケーションに変更または更新したアイテムをインポートします。 **注:** BizTalk アセンブリを更新するときに、停止し、.msi ファイルからインポートする前に成果物を参加解除する必要があります。 もう一度参加させるし、.msi からインポートした後、BizTalk アイテムを起動する必要があります。|-   [BizTalk アプリケーションをインポートする方法](http://go.microsoft.com/fwlink/?LinkId=154827)(http://go.microsoft.com/fwlink/?LinkId=154827)。<br />-   [アプリケーションを .msi ファイルからインポートする方法](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-のセクションの「BizTalk アプリケーションのインポート」[アプリケーションを展開するためのベスト プラクティス](../technical-guides/best-practices-for-deploying-an-application.md)です。<br />-   [BizTalk アプリケーションをインストールする方法](http://go.microsoft.com/fwlink/?LinkID=154728)(http://go.microsoft.com/fwlink/?LinkID=154728)。<br />-   [アセンブリを GAC にインストールする方法](http://go.microsoft.com/fwlink/?LinkId=154828)(http://go.microsoft.com/fwlink/?LinkId=154828)。|  
|メッセージの公開を再開する、アプリケーションを起動します。 すべての BizTalk ホスト インスタンスを再起動します。|-   [BizTalk アプリケーション開始および停止する方法](http://go.microsoft.com/fwlink/?LinkID=154729)(http://go.microsoft.com/fwlink/?LinkID=154729)。|  
|オーケストレーションを含むアセンブリをインポートした後に、インポート先のアプリケーションに、同じ名前、公開キー トークン、およびバージョンのアセンブリが既に存在する場合は、オーケストレーションのバインド先のホストのホスト インスタンスを停止および開始します。 これにより、アセンブリの新しいバージョンが BizTalk Server で使用されます。|-   [ホスト インスタンスを停止する方法](http://go.microsoft.com/fwlink/?LinkId=154829)(http://go.microsoft.com/fwlink/?LinkId=154829)。<br />-   [ホスト インスタンスを起動する方法](http://go.microsoft.com/fwlink/?LinkId=154830)(http://go.microsoft.com/fwlink/?LinkId=154830)。|