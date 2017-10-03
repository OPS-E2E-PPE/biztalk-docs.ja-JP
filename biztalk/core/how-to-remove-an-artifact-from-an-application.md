---
title: "アプリケーションからアイテムを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- artifacts, deleting
- applications, modifying
- applications, artifacts
- modifying, applications
- deleting, artifacts
ms.assetid: c528be0b-0b1a-4c5f-acd2-7355da91a253
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25d57c41311cef12a33685dcc4c8aacd85290b7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-an-artifact-from-an-application"></a>アプリケーションからアイテムを削除する方法
アイテムを削除すると、BizTalk Server データベースから削除され、管理コンソールまたは BTSTask ListApp コマンドで生成されるアプリケーションのアイテムの一覧には表示されなくなります。 アイテムが、Windows レジストリ、グローバル アセンブリ キャッシュ (GAC)、仮想ディレクトリ、またはファイル システムに存在する場合、これらの場所からは削除されません。 BizTalk 管理データベース内にのみ存在する送信ポート、送信ポート グループ、受信ポート、および受信場所の場合、アイテムはすべて削除されます。 背景情報について、次を参照してください[新機能の動作との成果物が追加および削除済み。](../core/what-happens-when-artifacts-are-added-and-removed.md)  
  
 アイテムの削除は、アイテムの種類に応じて、アプリケーションの機能にさまざまな影響を与える可能性があります。 特定の種類のアイテムの削除の詳細および手順については、以下に示す該当のトピックを参照してください。  
  
-   [オーケストレーションをアプリケーションから削除する方法](../core/how-to-remove-an-orchestration-from-an-application.md)  
  
-   [送信ポートを削除する方法](../core/how-to-delete-a-send-port.md)  
  
-   [送信ポート グループを削除する方法](../core/how-to-delete-a-send-port-group.md)  
  
-   [削除する方法、受信ポート](../core/how-to-delete-a-receive-port.md)  
  
-   [削除する方法、受信場所](../core/how-to-delete-a-receive-location.md)  
  
-   [アプリケーションと BizTalk グループからポリシーを削除する方法](../core/how-to-remove-a-policy-from-an-application-and-the-biztalk-group.md)  
  
-   [アプリケーションからスキーマを削除する方法](../core/how-to-remove-a-schema-from-an-application.md)  
  
-   [アプリケーションからマップを削除する方法](../core/how-to-remove-a-map-from-an-application.md)  
  
-   [アプリケーションから BizTalk アセンブリを削除する方法](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)  
  
-   [前または処理後のスクリプトをアプリケーションから削除する方法](../core/how-to-remove-a-pre-or-post-processing-script-from-an-application.md)  
  
-   [アプリケーションから .NET アセンブリ、証明書、またはその他のリソース アイテムを削除する方法](../core/remove-a-net-assembly-certificate-or-resource-artifact-from-an-application.md)  
  
## <a name="see-also"></a>参照  
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)   
 [RemoveResource コマンド](../core/removeresource-command.md)