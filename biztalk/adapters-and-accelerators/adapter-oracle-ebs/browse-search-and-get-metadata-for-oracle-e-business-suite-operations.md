---
title: 参照、検索、および Oracle E-business Suite 操作のメタデータを取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 05a0656c-84d0-4f25-9571-90a9df587b8c
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46588632c4444c5c38966cfc22fd75711d2af11a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996884"
---
# <a name="browse-search-and-get-metadata-for-oracle-e-business-suite-operations"></a>参照、検索、および Oracle E-business Suite 操作のメタデータを取得
このセクションを使用する方法について説明します、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] 、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]します。 これらを使用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ことができます、コンポーネント。  
  
- メタデータを取得する操作を参照します。  
  
- メタデータを取得する操作を検索します。  
  
- 選択した操作のメッセージ スキーマを追加し、ポートのバインドの構成ファイル、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]プロジェクトを使用する場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。  
  
- 使用する場合に、BizTalk 以外のプログラミング プロジェクトに WCF クライアント クラスまたは選択した操作と構成ファイル (app.config) の WCF サービス コントラクト (インターフェイス) を追加、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
## <a name="how-is-the-metadata-categorized"></a>メタデータの分類ですか。  
 [!INCLUDE[consumeadapterservshort_md](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]に接続する Oracle E-business Suite サーバーで使用できる成果物の 3 つの異なるビュー-**アプリケーション ベースのビュー**、**成果物ベースのビュー**、および**ビューのスキーマに基づく**します。 成果物の同じセットの 3 つの異なるビューを必要な理由。 次の表にリストするべき理由理由は、特定のビューを使用します。  
  
|表示|使用するは、|  
|----------|------------------------|  
|**アプリケーション ベースのビュー**|このビューは、Oracle E-business Suite アプリケーション名を使用して分類されます。 どのアプリケーションが使用する成果物を含むことがわかっている場合は、このビューを使用します。|  
|**成果物ベースのビュー**|このビューは、Oracle E-business Suite の成果物によって分類されます。 連携する Oracle E-business Suite の成果物が不明な成果物が属するどのアプリケーションがわかっている場合は、このビューを使用します。 このビューを使用すると、すべての Oracle E-business Suite アプリケーションで特定の成果物を検索できます。<br /><br /> 成果物ベースのビューには、PL-SQL Api、テーブル、ビュー、関数、プロシージャなどの基になる、Oracle データベースのアイテムも一覧表示されます。 これらの成果物はさらに、所属するスキーマに基づいて分類されます。 そのため、成果物ベースのビューの別の使用は、スキーマに属するアイテムおよびその他のスキーマに属している成果物を使用します。 このビューでは、すべてのスキーマ間でアイテムを検索することもできます。|  
|**スキーマ ベースのビュー**|このビューは、基になる Oracle データベースで使用できるスキーマによって分類されます。 スキーマが、成果物を使用することがわかっている場合は、このビューを使用します。 このビューでは、成果物として PL-SQL Api、プロシージャ、関数、テーブル、ビューとして分類されます。|  
  
 Oracle E-business Suite の成果物を分類する方法の詳細については、次を参照してください[アダプター メタデータの追加ウィザードを使用して Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-ebs-in-visual-studio-using-add-adapter-metadata-wizard.md)のアイテムを整理するためのもう 1 つの主な。別のビューは、簡単に特定のアイテムを検索します。 成果物を検索する方法の詳細については、[Oracle E-business Suite 操作の検索](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md)を参照してください。  
  
> [!IMPORTANT]
>  ノードが接続の接続を確立中に指定する URI に基づいて表示します。 Oracle E-business Suite の成果物に対するアクセス許可がありません。 資格情報を指定する場合は、で成果物を使用することはできません、**アプリケーション ベースのビュー**します。 また、**成果物ベースのビュー** Oracle E-business Suite に属するアイテムを一覧表示しません。  
  

  
## <a name="see-also"></a>参照  
 [Visual Studio での Oracle E-business Suite 操作のメタデータを取得します。](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)