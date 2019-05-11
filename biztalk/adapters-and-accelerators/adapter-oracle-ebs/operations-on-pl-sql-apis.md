---
title: PL-SQL Api の操作 |Microsoft Docs
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
ms.openlocfilehash: c65a1a6313b70b03894c2d4adc41d7679d71b82c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375326"
---
# <a name="operations-on-plsql-apis"></a>PL/SQL Api に対する操作
Oracle E-business Suite では、パッケージ化された関数およびストアド プロシージャの形式で PL/SQL Api のセットを提供します。 これらのパッケージ化関数とプロシージャでの操作として表示された[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。 

## <a name="plsql-apis-are-grouped-by-schema-names"></a>PL/SQL Api は、スキーマ名でグループ化されます。 
PL/SQL Api は、下にあるスキーマ名でグループ化されます、**成果物ベースのビュー**と**ビューのスキーマに基づく**Oracle E-business Suite に接続したときにノード[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. PL/SQL Api の参照については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[参照、検索、および Oracle E-business 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)します。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite でのアプリケーションだけでなく、Oracle データベースに関連付けられている PL/SQL Api が表示されます、**成果物ベースのビュー**と**ビューのスキーマに基づく**ノード。  
  
## <a name="important-info"></a>重要な情報
  -   Oracle E-business Suite でのアプリケーションに関連付けられている PL/SQL Api に対する操作を実行する前に、アプリケーションのコンテキストを設定する必要があります。 アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定とアーティファクトのアクセス制御を設定して Oracle E-business Suite でセキュリティで保護されたトランザクションを促進するためです。 ただし、Oracle データベースに関連付けられた PL/SQL Api のアプリケーションのコンテキストを設定する省略可能です。 参照してください[アプリケーション コンテキストを設定する](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  

- [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle PL/SQL API のパラメーターの既定値が割り当てられているかどうかを確認することはできません。  さらに、アダプターもできない確認パラメーターが必須または Oracle の PL/SQL API では省略可能として定義されているかどうか。 アダプターは、オプションのパラメーターとしてすべてのパラメーターを処理し、パラメーターの値が指定されていない場合です。  

  -   値で指定されている Oracle の既定値を使用し、既定値があります。  
  -   スローされる例外では、Oracle では必須のパラメーターとして定義されます。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)