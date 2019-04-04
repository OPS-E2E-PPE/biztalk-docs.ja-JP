---
title: Visual Studio で Siebel 操作のメタデータを取得 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving for Siebel operations in Visual Studio
ms.assetid: 63643942-6497-4891-ad7d-34b1df9acbc1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b4a7b6ed8cfd678d725323d92de045d27e10085
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014539"
---
# <a name="get-metadata-for-siebel-operations-in-visual-studio"></a>Visual Studio で Siebel 操作のメタデータを取得します。
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]は、2[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]アダプターを使用してソリューションを開発するために使用できるコンポーネントです。  
  
- [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]は BizTalk Server プロジェクトで使用できます。 使用する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] BizTalk ソリューションのターゲットに操作のメッセージ スキーマ (Xsd) を生成します。 BizTalk server ソリューションの開発に関する詳細については、[Siebel アダプターを使用して開発の BizTalk アプリケーション](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md)を参照してください。
  
- [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]は非 BizTalk プログラミング プロジェクトで使用できます。 使用する、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] WCF サービス モデルを使用してソリューションを開発するときに、WCF クライアント クラスまたは WCF サービスのコールバック インターフェイスを生成します。 WCF サービス モデルを使用したソリューションの開発に関する詳細については、[WCF サービス モデルを使用して開発の Siebel アプリケーション](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)を参照してください。  
  
  これらの両方の[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コンポーネントで開発を簡略化します。  
  
- ソリューションで使用する操作を参照および検索は、Microsoft Windows インターフェイスを提供します。  
  
- これらの操作のターゲットのアダプターによって公開されているメタデータを取得しています。  
  
- そのメタデータを変換するには、これによって表されます Web サービス記述言語 (WSDL) ドキュメントとしてアダプターは、ソリューション (BizTalk プロジェクトのメッセージ スキーマを XSD または wcf サービス コントラクトの .NET オブジェクトの表現で使用できる形式にサービス モデル)、プロジェクトに追加します。  
  
  このセクションでは使用する方法について説明、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  

  
## <a name="see-also"></a>参照  
[Siebel アプリケーションの開発](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)