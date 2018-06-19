---
title: アプリケーションまたはグループ内で一意である必要がありますの成果物 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- groups, artifacts
- artifacts, requirements
- applications, artifacts
ms.assetid: a758cd74-a962-4e75-aea2-47752ab72a64
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfe9ff033621ed491b7f1deae9e3f2e467e54f83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230386"
---
# <a name="artifacts-that-must-be-unique-in-an-application-or-group"></a>アプリケーションまたはグループ内で一意である必要があるアイテム
次に示すように、BizTalk グループまたはアプリケーション内の特定の種類のアイテムは一意であることが必要です。  
  
-   BizTalk アセンブリと BizTalk 以外の .NET アセンブリは、どちらもその完全な名前がグループ内で一意でなければなりません。 完全名は、ファイル名、公開キー トークン、カルチャ、およびバージョンで構成されます。  
  
-   ルールとポリシーの名前とバージョン番号は、グループ内で一意でなければなりません。  
  
-   送信ポート、送信ポート グループ、受信ポート、および受信場所の名前は、グループ内で一意でなければなりません。  
  
-   Web サイトの仮想ディレクトリ名はグループ内で一意でなければなりません。  
  
-   BAM リソースのファイル名はグループ内で一意でなければなりません。  
  
-   証明書の拇印はグループ内で一意でなければなりません。  
  
-   COM コンポーネントのファイル名は、グループ内で一意でなければなりません。  
  
-   スクリプトやその他のフラット ファイルなどのファイルベースのアイテムのファイル名は、アプリケーション内では一意でなければなりませんが、グループ内で一意である必要はありません。  
  
 アプリケーション内で一意でなければならない種類のアイテムをアプリケーションにインポートまたは追加する場合に、そのアイテムが既にアプリケーションに存在するときは、上書きオプションを指定できます。 グループ内で一意でなければならない種類のアイテムがグループ内の別のアプリケーションに存在する場合は、そのアイテムを追加またはインポートできません。  
  
 グループ内のあるアプリケーションで使用する必要があるアイテムが別のアプリケーションに既に存在する場合は、そのアイテムを含んでいるアプリケーションへの参照を作成できます。 詳細については、次を参照してください。[を別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)です。  
  
> [!NOTE]
>  表示するほとんどの成果物の種類の完全な名前、アプリケーションで、BTSTask の ListApp コマンドを使用して」の説明に従って[ListApp コマンド](../core/listapp-command.md)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの展開と管理を理解します。](../core/understanding-biztalk-application-deployment-and-management.md)