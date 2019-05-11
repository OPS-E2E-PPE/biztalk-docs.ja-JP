---
title: アプリケーションまたはグループ内で一意にする必要がある成果物 |Microsoft Docs
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
ms.openlocfilehash: 1dc28a438dff5e2fe21dc00d207da64fbdd2fc69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359260"
---
# <a name="artifacts-that-must-be-unique-in-an-application-or-group"></a>アプリケーションまたはグループ内で一意である必要があるアイテム
次に示すように、BizTalk グループまたはアプリケーション内の特定の種類のアイテムは一意であることが必要です。  
  
- BizTalk アセンブリと BizTalk 以外の .NET アセンブリは、どちらもその完全な名前がグループ内で一意でなければなりません。 完全名は、ファイル名、公開キー トークン、カルチャ、およびバージョンで構成されます。  
  
- ルールとポリシーの名前とバージョン番号は、グループ内で一意でなければなりません。  
  
- 送信ポート、送信ポート グループ、受信ポート、および受信場所の名前は、グループ内で一意でなければなりません。  
  
- Web サイトの仮想ディレクトリ名はグループ内で一意でなければなりません。  
  
- BAM リソースのファイル名はグループ内で一意でなければなりません。  
  
- 証明書の拇印はグループ内で一意でなければなりません。  
  
- COM コンポーネントのファイル名は、グループ内で一意でなければなりません。  
  
- スクリプトやその他のフラット ファイルなどのファイルベースのアイテムのファイル名は、アプリケーション内では一意でなければなりませんが、グループ内で一意である必要はありません。  
  
  アプリケーション内で一意でなければならない種類のアイテムをアプリケーションにインポートまたは追加する場合に、そのアイテムが既にアプリケーションに存在するときは、上書きオプションを指定できます。 グループ内で一意でなければならない種類のアイテムがグループ内の別のアプリケーションに存在する場合は、そのアイテムを追加またはインポートできません。  
  
  グループ内のあるアプリケーションで使用する必要があるアイテムが別のアプリケーションに既に存在する場合は、そのアイテムを含んでいるアプリケーションへの参照を作成できます。 詳細については、次を参照してください。[別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)します。  
  
> [!NOTE]
>  表示するほとんどの種類のアイテムの完全名、アプリケーションで、BTSTask の ListApp コマンドを使用して」の説明に従って[ListApp コマンド](../core/listapp-command.md)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの展開と管理について](../core/understanding-biztalk-application-deployment-and-management.md)