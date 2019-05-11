---
title: アイテムを追加または削除されたときの動作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, artifacts
- artifacts, deleting
- artifacts, creating
- deleting, artifacts
ms.assetid: 811166ba-3ff4-4224-9d84-a2f4ed31bf4d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbda3968ec4337ccf3b00bf1b1698d73c9232c47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401077"
---
# <a name="what-happens-when-artifacts-are-added-and-removed"></a>アイテムを追加または削除した場合の動作
このトピックでは、アプリケーションにアイテムを追加するときの動作について説明します。 ファイル ベースのアイテムは、BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用してアプリケーションを追加できます。 ファイル ベースのアイテムは、次の種類を含めます。  
  
-   BizTalk アセンブリ  
  
-   BizTalk に固有ではない .NET アセンブリ  
  
-   バインド (.xml) ファイル  
  
-   COM コンポーネント  
  
-   証明書  
  
-   処理前および処理後のスクリプト  
  
-   ポリシー  
  
-   Readme ファイルなどのアドホック ファイル  
  
-   仮想ディレクトリ  
  
-   BAM アイテム  
  
> [!NOTE]
>  送信ポート、送信ポート グループ、受信場所、および受信ポートは、ファイル ベースのアイテムでないし、アプリケーションに追加することはできません。 特定のアプリケーションでこれらの成果物を作成する必要があります。 できますしに移動する別のアプリケーションにする場合。 オーケストレーション、スキーマ、マップおよびパイプラインすべてデプロイし、管理を含むアセンブリの一部として。  
  
 アプリケーションにアイテムを追加して、成果物は、BizTalk 管理データベースでのアプリケーションに関連付けられた成果物のファイル ベースのデータは管理データベースに追加されます。 アプリケーションを簡単に転送することができ、管理データベースから .msi ファイルに、アプリケーションとそのアイテムのデータをエクスポートし、管理データベースにインポートできるので別に 1 つの BizTalk から成果物をグループ化します。別の BizTalk グループ。  
  
 バインド ファイルをアプリケーションに追加する場合は、バインドを適用する対象の展開環境を指定できます。 バインド ファイルをインポートするとは異なり、バインド ファイルを追加する場合は、そのバインドを適用することはできません。  
  
 BizTalk アセンブリまたは .NET アセンブリをアプリケーションに追加すると、このオプションを指定する場合、アセンブリがグローバル アセンブリ キャッシュに追加されます。  
  
## <a name="see-also"></a>参照  
 [アプリケーション展開中にアイテムを処理します。](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md)   
 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)   
 [BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)