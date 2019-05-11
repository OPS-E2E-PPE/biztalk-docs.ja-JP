---
title: Visual Studio での Oracle E-business Suite 操作のメタデータを取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87d7f731-cd0f-4970-a3cd-072f09312989
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77977351036e86e558491a2c2927a29878ae550b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375527"
---
# <a name="get-metadata-for-oracle-e-business-suite-operations-in-visual-studio"></a>Visual Studio での Oracle E-business Suite 操作のメタデータを取得します。
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] 3 つ提供[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネント。  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]  
  
- [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]  
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]  
  
  アダプター クライアントは、これらのコンポーネントを使用して Oracle E-business Suite に接続しを実行する操作のメタデータを生成する必要があります。 これらはすべて[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントで開発を簡略化します。  
  
- ソリューションで使用する操作を参照および検索は、Microsoft Windows インターフェイスを提供します。  
  
- これらの操作のターゲットのアダプターによって公開されているメタデータを取得しています。  
  
- そのメタデータを変換するには、これによって表されます Web サービス記述言語 (WSDL) ドキュメントとしてアダプターは、ソリューション (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクトの表現で使用できる形式にサービス モデル)、プロジェクトに追加します。  
  
  このセクションでは使用する方法について説明、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
> [!NOTE]
>  Oracle E-business Suite では、特定のバージョンのアダプターを使用してソリューションを作成した別のバージョンの Oracle E-business Suite でソリューションを展開しようとする場合は、展開する前に、ソリューションをテストする必要があります。 基になる成果物のメタデータが異なる可能性があるために、別のバージョンの Oracle E-business Suite のソリューションをデプロイするときに問題が発生する可能性があります。 この問題を解決するには、Oracle E-business Suite のソリューションを配置するのと同じバージョンのアダプターを使用してメタデータを再生成する必要があります。  
  
