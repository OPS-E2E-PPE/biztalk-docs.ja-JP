---
title: 成果物の追加または削除されるときの動作 |Microsoft ドキュメント
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
ms.openlocfilehash: 464964714993205ef65d5a67de3399935f79320f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288882"
---
# <a name="what-happens-when-artifacts-are-added-and-removed"></a>アイテムを追加または削除した場合の動作
このトピックでは、アプリケーションにアイテムを追加した場合の動作について説明します。 BizTalk Server 管理コンソールまたは BTSTask コマンド ライン ツールを使用して、ファイルベースのアイテムをアプリケーションに追加することができます。 ファイルベースのアイテムには、次の種類のものがあります。  
  
-   BizTalk アセンブリ  
  
-   BizTalk に固有でない .NET アセンブリ  
  
-   バインド (.xml) ファイル  
  
-   COM コンポーネント  
  
-   証明書  
  
-   処理前および処理後のスクリプト  
  
-   ポリシー  
  
-   アドホック ファイル (Readme ファイルなど)  
  
-   仮想ディレクトリ  
  
-   BAM アイテム  
  
> [!NOTE]
>  送信ポート、送信ポート グループ、受信場所、および受信ポートはファイルベースのアイテムではないため、アプリケーションに追加することはできません。 これらのアイテムは、特定のアプリケーションで作成する必要があります。 作成後に、必要に応じて他のアプリケーションに移動することができます。 オーケストレーション、スキーマ、マップ、およびパイプラインは、これらを含むアセンブリの一部として、展開および管理します。  
  
 アイテムをアプリケーションに追加すると、そのアイテムは BizTalk 管理データベースのアプリケーションに関連付けられ、アイテムのファイル ベースのデータも管理データベースに追加されます。 これにより、アプリケーションとそのアイテムのデータを管理データベースから .msi ファイルにエクスポートし、そのファイルを他の BizTalk グループの管理データベースにインポートするだけで、アプリケーションおよびアイテムを移動できます。  
  
 アプリケーションにバインド ファイルを追加する場合は、バインドを適用する対象の展開環境を指定することができます。 バインド ファイルのインポートとは異なり、バインド ファイルを追加しても、そのバインドは適用されません。  
  
 BizTalk アセンブリまたは .NET アセンブリをアプリケーションに追加する場合は、このオプションを選択すると、アセンブリがグローバル アセンブリ キャッシュに追加されます。  
  
## <a name="see-also"></a>参照  
 [アプリケーションの展開時の成果物を処理します。](../core/what-happens-to-artifacts-during-application-deployment.md)   
 [成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md)   
 [BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)   
 [BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)