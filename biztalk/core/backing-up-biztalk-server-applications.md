---
title: BizTalk Server アプリケーションのバックアップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b51e3ae6-08ed-48ca-8977-13f46144a5fa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5f209ea114cb515e0d09f5ddd80bbf864501038
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530613"
---
# <a name="backing-up-biztalk-server-applications"></a>BizTalk Server アプリケーションのバックアップ
ハードウェア障害の後、BizTalk Server システムを回復できることを確認するには、適切なバックアップがある必要があります。 、ままの状態のバックアップの一部としては、BizTalk アプリケーションをリモート サーバーをエクスポートして、これらのアプリケーションをバックアップすることをお勧めします。  
  
 後で、BizTalk Server データベースを復元して、BizTalk Server を再インストールするときに、これらのアプリケーションをインポートできます。 エクスポートして、アプリケーションをインポートする方法の詳細については、次を参照してください。 [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md)します。  
  
 コンピューターに展開されているすべての BizTalk アプリケーションを .msi ファイルをエクスポートして (別のサーバー) 上のバックアップ場所に保存をします。 .Msi ファイルを使用すると、セットアップ先のコンピューターを回復した後に、BizTalk Server で必要なリソースを再インストールできます。 .Msi ファイルに、必要なリソースが含まれていると、これらのリソースの .msi のインストールで実行するアクションを指定することを確認してください。 場合は、BizTalk アプリケーションは、すべてのユーザー アセンブリまたは .msi ファイルに含まれていないその他の Dll に依存する必要がありますをバックアップすることを個別にします。  
  
 アプリケーションのエクスポート手順は、オーケストレーションのシナリオと、コンテンツ ベース ルーティングのシナリオと同じです。 BizTalk アプリケーションを変更するたびに、このプロセスが繰り返されます。 詳細については、次を参照してください。 [BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)