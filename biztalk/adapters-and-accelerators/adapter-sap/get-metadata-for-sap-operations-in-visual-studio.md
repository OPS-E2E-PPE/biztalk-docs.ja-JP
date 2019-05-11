---
title: Visual Studio で SAP 操作のメタデータを取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving for SAP operations in Visual Studio
ms.assetid: 1be5934a-a5d4-4734-8bea-fb8274f59c71
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 338130847a220d16cd4b5e42c1f93ff2bc3b2334
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373408"
---
# <a name="get-metadata-for-sap-operations-in-visual-studio"></a>Visual Studio で SAP 操作のメタデータを取得します。
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]は、2[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネント:、 [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 アダプター クライアントは、これらのコンポーネントを使用して、SAP システムに接続し、呼び出し先 SAP アイテムのメタデータを生成する必要があります。  
  
 これらはすべて[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントで開発を簡略化します。  
  
- ソリューションで使用する操作を参照および検索は、Microsoft Windows インターフェイスを提供します。  
  
- これらの操作のターゲットのアダプターによって公開されているメタデータを取得しています。  
  
- そのメタデータを変換するには、これによって表されます Web サービス記述言語 (WSDL) ドキュメントとしてアダプターは、ソリューション (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクトの表現で使用できる形式にサービス モデル)、プロジェクトに追加します。  
  
  このセクションでは使用する方法について説明、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、 [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]、および[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
 
  
## <a name="see-also"></a>参照  
[SAP アプリケーションを開発する](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)