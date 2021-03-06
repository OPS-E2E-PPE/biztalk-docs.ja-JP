---
title: 関数およびストアド Procedures1 に対する操作 |Microsoft Docs
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
ms.openlocfilehash: c0c108490d9ce280f6926bc66ba2d2665254f636
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375333"
---
# <a name="operations-on-functions-and-stored-procedures"></a>関数とストアド プロシージャに対する操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] Oracle 関数およびプロシージャをサポートしています。

## <a name="functions-and-procedures"></a>関数およびプロシージャ

[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]次のように Oracle 関数およびプロシージャをサポートしています。  
  
- **関数**操作として表示されます。 操作の名前は、Oracle 関数の名前です。 出し、および OUT パラメーターはサポートされてだけでなく、戻り値。  
  
  > [!IMPORTANT]
  >  無効なパラメーターを関数に渡す場合 (つまり、数値フィールドの文字列値を渡す)、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET 動作によって例外をスローする可能性があります。 これは、ため、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ODP.NET を使用して Oracle E-business Suite と通信します。  
  
- **プロシージャ**操作として表示されます。 操作の名前は、Oracle のプロシージャの名前です。 出し、および OUT パラメーターはサポートされています。  
  
  > [!IMPORTANT]
  >  挿入またはインターフェイスのテーブルまたはデータベースのテーブルの数値フィールドに (たとえば、15.2) の 10 進値を更新する場合、プロシージャの一部として、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]例外がスローされます。 これは、ため、 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite と通信するために ODP.NET、ODP.NET は数値フィールドの 10 進数の値をそのまま使用します。  
  
- **REF CURSOR 型**IN はサポートされており、OUT パラメーターをプロシージャと関数、および関数の戻り値。 詳細については、次を参照してください。[関数および REF CURSOR パラメーターを使用したプロシージャに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-ref-cursor-parameters1.md)します。  
  
- **レコードの種類**IN はサポートされておりで OUT パラメーターをプロシージャと関数、および関数の戻り値。 単純および複雑な両方の (入れ子になった) レコードの種類がサポートされています。 [RECORD 型を使用した関数およびプロシージャに対する操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-functions-and-procedures-with-record-types1.md)  
  
> [!NOTE]
>  関数およびストアド プロシージャでのアプリケーションのコンテキストを設定することもできます。[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。 アプリケーションのコンテキスト、および設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
## <a name="see-also"></a>参照  
 [どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)