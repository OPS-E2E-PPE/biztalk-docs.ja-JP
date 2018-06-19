---
title: 関数およびストアド Procedures1 に対する操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1e6bdaa7-ed3c-43bc-bed5-70fe43f9c2d1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cfe5f705c8e432c920c8fae41a2b2f050c188047
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216354"
---
# <a name="operations-on-functions-and-stored-procedures"></a>関数およびストアド プロシージャでの操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle 関数およびプロシージャをサポートしています。

## <a name="functions-and-procedures"></a>関数およびプロシージャ

[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]次のように Oracle 関数およびプロシージャをサポートしています。  
  
-   **関数**操作として表示されます。 操作の名前は、Oracle 関数の名前です。 出し、および OUT パラメーターはサポートし、同様に、値を返します。  
  
    > [!IMPORTANT]
    >  関数で無効なパラメーターを渡す場合 (つまり、数値フィールドの文字列値、渡す、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET 動作によって例外をスローする可能性があります。 これは、ため、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET を使用して Oracle E-business Suite と通信します。  
  
-   **プロシージャ**操作として表示されます。 操作の名前は、Oracle のプロシージャの名前です。 出し、および OUT パラメーターはサポートされています。  
  
    > [!IMPORTANT]
    >  挿入またはインターフェイスのテーブルまたはデータベース テーブルの数値フィールドに (たとえば、15.2) の 10 進値を更新する場合、プロシージャの一部として、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]例外がスローされます。 これは、ため、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite と通信するために ODP.NET、ODP.NET はサポートしていません数値フィールドの 10 進数の値をそのまま使用します。  
  
-   **REF CURSOR 型**IN はサポートされてし、OUT パラメーター プロシージャおよび関数、および関数の戻り値。 詳細については、次を参照してください。[関数および REF CURSOR パラメーターを持つプロシージャで操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)です。  
  
-   **レコードの種類**はサポートされて IN、OUT、おりで OUT パラメーター プロシージャおよび関数、および関数の値を返します。 単純または複雑なの両方の (入れ子になった) レコードの種類がサポートされています。 [関数およびレコードの種類のプロシージャでの操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
> [!NOTE]
>  関数およびストアド プロシージャでのアプリケーション コンテキストを設定することもできます。[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。 アプリケーションのコンテキストとそれを設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
## <a name="see-also"></a>参照  
 [どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)