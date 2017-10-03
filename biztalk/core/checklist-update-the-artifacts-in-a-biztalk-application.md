---
title: "チェックリスト: BizTalk アプリケーション内のアイテムの更新 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, redeploying
- updating, applications
- redeploying
- checklists, applications
- updating, checklists
- updating
- applications, updating
- applications, redeploying
- applications, checklists
- checklists, redeploying
ms.assetid: 07ea4a2b-4ada-4d04-9eec-604b63b77415
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 321ef2c6c9bbd522c54f5d9352995788d8843455
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-update-the-artifacts-in-a-biztalk-application"></a>チェックリスト: BizTalk アプリケーション内のアイテムを更新します。
既に展開されているアプリケーションで 1 つ以上のアイテムを変更または更新する場合はこのチェック リストの作業を実行し、アプリケーションを再展開します。  
  
|手順|リファレンス|  
|----------|---------------|  
|アプリケーションでアイテムを更新するための重要な考慮事項を確認します。|[アプリケーションを更新するための重要な考慮事項](../core/important-considerations-for-updating-applications.md)|  
|展開を実行するための適切なアクセス許可があることを確認します。|[展開して、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)|  
|Visual Studio でアセンブリに必要な変更を行います。 実稼働環境で実行されているアセンブリを更新する場合は、常にアセンブリ バージョン番号を増やす必要があります。 背景情報について、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)です。 次に、開発環境で Visual Studio から BizTalk アプリケーションにアセンブリを展開します。|[Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)|  
|新しいアイテムまたは変更されたアイテムをテストします。新しいアイテムまたは変更されたアイテムに依存する可能性があるすべてのアイテムもテストします。 テスト中、このアプリケーションとその他のアプリケーション間に存在する依存関係を考慮します。|[BizTalk アプリケーションの展開のテスト作業](../core/testing-tasks-for-biztalk-application-deployment.md)|  
|必要に応じて、アプリケーションでアイテムを追加、削除、または再構成します。|[成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md)、[アプリケーションからアイテムを削除する方法](../core/how-to-remove-an-artifact-from-an-application.md)、[成果物の管理](../core/managing-artifacts.md)|  
|新しいアイテムや変更されたアイテムを含むアプリケーションを .msi ファイルにエクスポートします。 アプリケーション内のすべてのアイテム、または追加、更新するアイテムをエクスポートできます。 ファイル アイテムは上書きされる可能性があることに注意してください。 ファイル アイテムをエクスポートする場合は、アプリケーションで使用するバージョンであることを確認します。|[BizTalk アプリケーション、バインド、およびポリシーをエクスポートします。](../core/exporting-biztalk-applications-bindings-and-policies.md)|  
|更新が、その更新を実行しているアプリケーションの妨げになる場合は、更新するアプリケーションを停止します。 アセンブリを新しいバージョンで更新する場合は、アプリケーションを再起動する必要はありません。 **注:**アイテムを更新したり、アプリケーションをインストールするためにアプリケーションを停止する必要はありませんをアイテムを更新するときに常にアプリケーションを停止することお勧めします。|[BizTalk アプリケーション開始および停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)|  
|変更または更新したアイテムを、.msi ファイルから更新対象のアプリケーションにインポートします。 既存のアイテムを上書きするオプションを指定してください。|[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)|  
|更新されたアプリケーションまたはアイテムを .msi ファイルから、アプリケーションが実行されているすべてのコンピューター、およびこのアプリケーションに依存するアプリケーションを実行しているすべてのコンピューターにインストールします。 BizTalk アセンブリを更新する場合は、アセンブリの新しいバージョンが、そのアセンブリを実行している各コンピューターのグローバル アセンブリ キャッシュ (GAC) にインストールされていることを確認します。 インストールされていない場合は、各 GAC にアセンブリをインストールします。|[BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)、 [GAC でアセンブリをインストールする方法](../core/how-to-install-an-assembly-in-the-gac.md)|  
|アプリケーションを起動します。|[BizTalk アプリケーション開始および停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)|  
|オーケストレーションを含むアセンブリをインポートした後に、インポート先のアプリケーションに、同じ名前、公開キー トークン、およびバージョンのアセンブリが既に存在する場合は、オーケストレーションのバインド先のホストのホスト インスタンスを停止および開始します。 これにより、アセンブリの新しいバージョンが BizTalk Server で使用されます。|[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)、[ホスト インスタンスを起動する方法](../core/how-to-start-a-host-instance.md)|  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの展開と管理のチェックリスト](../core/biztalk-application-deployment-and-management-checklists.md)   
 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)