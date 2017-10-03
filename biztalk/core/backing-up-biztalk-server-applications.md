---
title: "BizTalk Server アプリケーションのバックアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b51e3ae6-08ed-48ca-8977-13f46144a5fa
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d125a1430aa2d044abba7632fa31a9c89f2bc50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-biztalk-server-applications"></a>BizTalk Server アプリケーションのバックアップ
ハードウェア障害が発生した後、BizTalk Server システムを確実に復旧するには、適切なバックアップを作成しておくことが重要です。 バックアップ計画では、BizTalk アプリケーションをリモート サーバーにエクスポートし、アプリケーションをバックアップすることをお勧めします。  
  
 こうしておくと、後で BizTalk Server データベースを復元して BizTalk Server を再インストールしたときに、バックアップしたアプリケーションをインポートできます。 エクスポートして、アプリケーションをインポートする方法の詳細については、次を参照してください。[を管理する BizTalk アプリケーションの展開と](../core/deploying-and-managing-biztalk-applications.md)です。  
  
 コンピュータに展開されているすべての BizTalk アプリケーションについて、.msi ファイルをエクスポートし、別のサーバー上のバックアップ場所に保存してください。 .msi ファイルを使用すると、コンピュータを復旧した後で BizTalk Server に必要なリソースを再インストールできます。 .msi には必要なリソースをすべて含め、これらのリソースを .msi ファイルでインストールするときに必要な手順も指定しておきます。 BizTalk アプリケーションが、.msi ファイルに含まれていないユーザー アセンブリやその他の DLL に依存している場合は、これらのコンポーネントも別にバックアップする必要があります。  
  
 アプリケーションのエクスポート手順は、コンテンツ ベースのルーティングやオーケストレーションが含まれる場合でも同じです。 BizTalk アプリケーションを変更したときには、常にこの手順を実行する必要があります。 詳細については、次を参照してください。[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk Server を実行しているコンピューターのバックアップ](../core/backing-up-a-computer-running-biztalk-server.md)