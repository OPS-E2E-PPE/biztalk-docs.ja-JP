---
title: "Visual Studio での Oracle E-business Suite 操作のメタデータを取得 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87d7f731-cd0f-4970-a3cd-072f09312989
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97ef4cc308979718f306958d0da1bb1eceaebaf8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-for-oracle-e-business-suite-operations-in-visual-studio"></a>Visual Studio での Oracle E-business Suite 操作のメタデータを取得します。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] 3 つの提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネント。  
  
-   [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]  
  
-   [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]  
  
-   [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]  
  
 アダプター クライアントは、これらのコンポーネントを使用して Oracle E-business Suite に接続しを実行する操作のメタデータを生成する必要があります。 これらはすべて[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントでの開発を簡略化します。  
  
-   ソリューションで使用する操作を使用するには、参照および検索することができます、Microsoft Windows インターフェイスを提供します。  
  
-   これらのターゲット操作用にアダプターによって公開されるメタデータを取得しています。  
  
-   そのメタデータを変換するとして表される Web サービス記述言語 (WSDL) ドキュメント、アダプターによって (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクト表現は、ソリューションで使用できるフォームサービス モデル) し、プロジェクトに追加します。  
  
 このセクションで説明を使用する手順については、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
> [!NOTE]
>  Oracle E-business Suite の特定のバージョンのアダプターを使用してソリューションを作成した別のバージョンの Oracle E-business Suite でソリューションを展開していて、展開する前に、ソリューションをテストする必要があります。 基になる成果物のメタデータが異なる可能性があるため、異なるバージョンの Oracle E-business Suite でソリューションの展開中に問題に直面可能性があります。 この問題を解決するには、同じバージョンのソリューションを配置する Oracle E-business Suite でアダプターを使用してメタデータを再生成する必要があります。  
  
