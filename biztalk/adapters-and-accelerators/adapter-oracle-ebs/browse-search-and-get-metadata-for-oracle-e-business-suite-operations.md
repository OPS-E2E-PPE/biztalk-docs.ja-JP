---
title: "参照、検索、および Oracle E-business Suite 操作のメタデータを取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 05a0656c-84d0-4f25-9571-90a9df587b8c
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a26b13ddef6efe9214e7d889d5d8e02d2f1505cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-metadata-for-oracle-e-business-suite-operations"></a>参照、検索、および Oracle E-business Suite 操作のメタデータを取得
このセクションで説明を使用する方法については、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]と[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。 これらを使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネント、することができます。  
  
-   メタデータを取得する操作を参照します。  
  
-   メタデータを取得する操作を検索します。  
  
-   選択した操作のメッセージ スキーマを追加し、ポートのバインドの構成ファイル、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトを使用する場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。  
  
-   WCF クライアント クラスまたは WCF サービス コントラクト (インターフェイス) を選択した操作と構成ファイル (app.config) を使用する場合、BizTalk 以外のプログラミング プロジェクトを追加、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
## <a name="how-is-the-metadata-categorized"></a>メタデータの分類ですか。  
 [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]接続先 Oracle E-business Suite のサーバーで使用できる成果物の 3 つの異なるビュー-**アプリケーション ベースのビュー**、**成果物に基づいたビュー**、および**ビューのスキーマに基づく**です。 成果物の同じセットの 3 つの異なるビューをおく理由 次の表にリストするすべき理由、理由は、特定のビューを使用します。  
  
|表示|使用しているとき|  
|----------|------------------------|  
|**アプリケーション ベースのビュー**|このビューは、Oracle E-business Suite アプリケーション名を使用して分類されます。 どのアプリケーションが操作する成果物を含むことがわかっている場合に、このビューを使用します。|  
|**成果物ベースのビュー**|このビューは、Oracle E-business Suite の成果物によって分類されます。 連携する Oracle E-business Suite の成果物を確信できない成果物が属するどのアプリケーションがわかっている場合に、このビューを使用します。 このビューを使用して、検索できます、特定の成果物のすべての Oracle E-business Suite アプリケーション。<br /><br /> 成果物ベースのビューには、PL-SQL Api、テーブル、ビュー、関数、プロシージャなど、基になる Oracle データベース内の成果物も一覧表示します。 これらの成果物は、所属するスキーマに基づいてさらに分類されます。 そのため、成果物に基づくビューの別の使用は、スキーマに属している成果物とその他のスキーマに属している成果物を使用するは。 このビューでは、すべてのスキーマ間でアイテムを検索することもできます。|  
|**スキーマ ベースのビュー**|このビューは、基になる Oracle データベースで使用可能なスキーマで分類されます。 スキーマが使用するアイテムがわかっている場合に、このビューを使用します。 この表示では PL-SQL Api、プロシージャ、関数、テーブル、およびビューとして分類との成果物です。|  
  
 Oracle E-business Suite の成果物を分類する方法の詳細については、次を参照してください[アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md)の成果物を整理するための別のキー理由。さまざまなビューは、特定のアイテムを検索するように簡単です。 成果物を検索する方法の詳細については、次を参照してください。 [Oracle E-business Suite 操作の検索](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md)です。  
  
> [!IMPORTANT]
>  ノードは表示、接続の接続を確立中に指定する URI に基づいて。 Oracle E-business Suite の成果物にアクセス許可がない資格情報を指定する場合は、内の成果物を使用することはできません、**アプリケーション ベースのビュー**です。 また、**成果物に基づいたビュー** Oracle E-business Suite に属している成果物を一覧表示しません。  
  

  
## <a name="see-also"></a>参照  
 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)