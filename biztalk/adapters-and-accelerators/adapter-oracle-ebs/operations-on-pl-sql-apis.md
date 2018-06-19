---
title: PL-SQL Api に対する操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d47b894d-1047-48ed-8f8c-865c343a12db
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5462bc4b4d6ee6a55e0e14d3ca9fccabc4dc2daf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216010"
---
# <a name="operations-on-plsql-apis"></a>PL/SQL Api に対する操作
Oracle E-business Suite では、一連のパッケージ化された関数およびストアド プロシージャの形式で PL/SQL Api を提供します。 これらのパッケージ化された関数およびプロシージャでの操作として表示された[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]です。 

## <a name="plsql-apis-are-grouped-by-schema-names"></a>PL/SQL Api はスキーマ名でグループ化します。 
PL/SQL Api は、下にあるスキーマ名でグループ化、**成果物に基づいたビュー**と**ビューのスキーマに基づく**Oracle E-business Suite を使用して接続するときにノード[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. PL/SQL の Api を参照する方法については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[参照、検索、および Oracle E-business 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)です。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite でアプリケーションだけでなく、Oracle データベースに関連付けられている PL/SQL Api を表示、**成果物ベースのビュー**と**ビューのスキーマに基づく**ノード。  
  
## <a name="important-info"></a>重要な情報
  -   Oracle E-business suite アプリケーションに関連付けられている PL/SQL Api に対する操作を行うことができます、前に、アプリケーションのコンテキストを設定する必要があります。 アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定、およびアイテムのアクセス制御を設定して Oracle E-business Suite でセキュリティ保護されたトランザクションを容易にするためです。 ただし、Oracle データベースに関連付けられている PL/SQL Api のアプリケーションのコンテキストを設定する省略可能なは。 参照してください[アプリケーション コンテキストを設定する](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  

-   [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle で PL/SQL API 内のパラメーターの既定値が割り当てられているかどうかを確認することはできません。  さらに、アダプターもできない確認パラメーターが必須または Oracle の PL/SQL API では省略可能として定義されているかどうか。 アダプターは、オプションのパラメーターとしてすべてのパラメーターを処理し、パラメーターの値が指定されていない場合です。  

    -   デフォルト値で指定されている Oracle の既定値を使用しています。  
    -   スローされる例外では、Oracle では、必須のパラメーターとして定義されます。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)