---
title: チェックリスト:BizTalk アプリケーション内のアイテムの更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a061b121b8a50f8338a6459baa7b3f7ff379bf1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357773"
---
# <a name="checklist-update-the-artifacts-in-a-biztalk-application"></a>チェックリスト:BizTalk アプリケーション内のアイテムを更新します。
このチェックリストの手順を変更したり、既にデプロイされているアプリケーションで 1 つまたは複数のアイテムを更新する場合と、アプリケーションを再デプロイします。  
  
|手順|リファレンス|  
|----------|---------------|  
|アプリケーションでアイテムを更新するための重要な考慮事項を確認します。|[アプリケーションの更新に関する重要な考慮事項](../core/important-considerations-for-updating-applications.md)|  
|配置を実行する適切なアクセス許可があることを確認します。|[BizTalk アプリケーションの展開と管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)|  
|Visual Studio でアセンブリに必要な変更を加えます。 実稼働環境で実行されているアセンブリを更新する場合は、常にアセンブリ バージョン番号を増やす必要があります。 背景情報は、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)します。 Visual Studio からアセンブリを開発環境での BizTalk アプリケーションに展開します。|[Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)|  
|新規または変更された成果物に依存するすべてのアイテムもテストすることを確認、新しいまたは変更されたアイテムをテストします。 テスト中、必ずこのアプリケーションとその他のアプリケーション間に存在する依存関係を考慮してください。|[BizTalk アプリケーション展開のテスト作業](../core/testing-tasks-for-biztalk-application-deployment.md)|  
|追加、削除、または必要に応じて、アプリケーション内のアイテムを再構成します。|[成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md)、[アプリケーションからアイテムを削除する方法](../core/how-to-remove-an-artifact-from-an-application.md)、[成果物の管理](../core/managing-artifacts.md)|  
|.Msi ファイルに追加または変更された成果物を含むアプリケーションをエクスポートします。 すべてのアプリケーションのアイテムまたは追加または更新するアイテムのみをエクスポートすることがありますか。 ファイル アイテムを上書きできることに注意します。 ファイル成果物をエクスポートする場合は、アプリケーションで使用するバージョンであることを確認します。|[BizTalk アプリケーション、バインド、およびポリシーのエクスポート](../core/exporting-biztalk-applications-bindings-and-policies.md)|  
|実行時に、更新プログラムは、アプリケーションを妨げる場合、は、更新するアプリケーションを停止します。 新しいバージョンのアセンブリを更新する場合は、アプリケーションを再起動する必要はありません。 **注:** アイテムを更新したり、アプリケーションをインストールするためにアプリケーションを停止する必要はありませんが、アイテムを更新する場合は常にアプリケーションを停止することをお勧めします。|[BizTalk アプリケーション開始および停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)|  
|.Msi ファイルから更新するアプリケーションに変更または更新した成果物をインポートします。 既存のアイテムを上書きするオプションを指定することを確認します。|[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)|  
|すべてのアプリケーションを実行するコンピューターだけでなくこのアプリケーションに依存するアプリケーションを実行しているコンピューター上に .msi ファイルから更新されたアプリケーションまたは成果物をインストールします。 BizTalk アセンブリを更新する場合は、アセンブリを実行する各コンピューターにグローバル アセンブリ キャッシュ (GAC) にアセンブリの新しいバージョンがインストールされていることを確認します。 それ以外の場合は、各 GAC にアセンブリをインストールします。|[BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)、[を GAC にアセンブリをインストールする方法](../core/how-to-install-an-assembly-in-the-gac.md)|  
|アプリケーションを起動します。|[BizTalk アプリケーション開始および停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)|  
|オーケストレーションを含むアセンブリをインポートした後、停止をインポートする、既にアプリケーションに同じ名前、公開キー トークン、およびバージョンを持つアセンブリが含まれている場合と、オーケストレーションをホストのホスト インスタンスを開始します。バインドされています。 これにより、BizTalk Server によって、アセンブリの新しいバージョンを使用します。|[ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)、[ホスト インスタンスを開始する方法](../core/how-to-start-a-host-instance.md)|  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの展開と管理のチェックリスト](../core/biztalk-application-deployment-and-management-checklists.md)   
 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)