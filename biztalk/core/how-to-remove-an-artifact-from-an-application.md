---
title: アプリケーションからアイテムを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- artifacts, deleting
- applications, modifying
- applications, artifacts
- modifying, applications
- deleting, artifacts
ms.assetid: c528be0b-0b1a-4c5f-acd2-7355da91a253
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c9c891b297ceb336d14f8964dd71d71b4fe28af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384317"
---
# <a name="how-to-remove-an-artifact-from-an-application"></a>アプリケーションからアイテムを削除する方法
削除または成果物の削除は、管理コンソールまたは BTSTask ListApp コマンドによって生成されたアプリケーションのアイテムの一覧に表示されないように、BizTalk Server データベースから削除します。 これらの場所のいずれかに存在する場合、成果物、Windows レジストリ、グローバル アセンブリ キャッシュ (GAC)、仮想ディレクトリ、または、ファイル システムから削除されません。 送信ポートの場合は、送信ポート グループ、受信ポート、および場所で、削除を BizTalk 管理データベース、この操作にのみ存在、成果物をまったく受信します。 背景情報は、次を参照してください[何の動作と成果物が追加および削除。](../core/what-happens-when-artifacts-are-added-and-removed.md)  
  
 削除するか、成果物を削除するには、成果物の種類に応じて、アプリケーションの機能にさまざまな効果を持つことができます。 詳細と手順を削除するか、特定の種類の成果物の削除については、次のように、該当するトピックを参照してください。  
  
-   [オーケストレーションをアプリケーションから削除する方法](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [送信ポートを削除する方法](../core/how-to-delete-a-send-port.md)  
  
-   [送信ポート グループを削除する方法](../core/how-to-delete-a-send-port-group.md)  
  
-   [削除する方法、受信ポート](../core/how-to-delete-a-receive-port.md)  
  
-   [削除する方法、受信場所](../core/how-to-delete-a-receive-location.md)  
  
-   [アプリケーションおよび BizTalk グループからポリシーを削除する方法](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [アプリケーションからスキーマを削除する方法](../core/how-to-remove-a-schema-from-an-application.md)  
  
-   [アプリケーションからマップを削除する方法](../core/how-to-remove-a-map-from-an-application.md)  
  
-   [アプリケーションから BizTalk アセンブリを削除する方法](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)  
  
-   [処理前または処理後のスクリプトをアプリケーションから削除する方法](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)  
  
-   [アプリケーションから .NET アセンブリ、証明書、またはその他のリソース アイテムを削除する方法](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)  
  
## <a name="see-also"></a>参照  
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)   
 [RemoveResource コマンド](../core/removeresource-command.md)