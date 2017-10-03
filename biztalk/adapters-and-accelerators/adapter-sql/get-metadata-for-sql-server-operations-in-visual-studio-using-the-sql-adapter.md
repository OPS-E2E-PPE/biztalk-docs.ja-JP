---
title: "SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a7ac720-e573-4564-8d15-8212a815f1f7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec993dd308abf0f364eb73f6f35d48d618d6807e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter"></a>SQL アダプターを使用して Visual Studio での SQL Server 操作のメタデータを取得します。
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] 3 つの提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネント:、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]です。 アダプターのクライアントは、SQL Server に接続しを実行する操作のメタデータを生成するこれらのコンポーネントを使用する必要があります。  
  
 これらはすべて[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントでの開発を簡略化します。  
  
-   ソリューションで使用する操作を使用するには、参照および検索することができます、Microsoft Windows インターフェイスを提供します。  
  
-   これらのターゲット操作用にアダプターによって公開されるメタデータを取得しています。  
  
-   そのメタデータを変換するとして表される Web サービス記述言語 (WSDL) ドキュメント、アダプターによって (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクト表現は、ソリューションで使用できるフォームサービス モデル) し、プロジェクトに追加します。  
  
 このセクションで説明を使用する手順については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
