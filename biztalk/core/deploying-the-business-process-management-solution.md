---
title: "ビジネス プロセス管理ソリューションの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, process management solution tutorial
- process management solution tutorial, deploying
ms.assetid: e033e0cd-0333-4f16-a4a0-eaae9ce98fcc
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0a61048ecb90876b251657f00361c35587a7ec1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="deploying-the-business-process-management-solution"></a>ビジネス プロセス管理ソリューションの展開
ビジネス プロセス管理 (BPM) ソリューションは、BizTalk アプリケーションのプロセス マネージャを構築する方法の 1 つです。 このソリューションでは、1 つのコンポーネントを使用して、注文処理に含まれる一連のステージを選択および制御します。 ソリューションが注文を取得: 新しいサービス、アップグレード、またはサービスの終了の可能性もあります-ログの記録、および処理するため渡す前に、順序を確認します。 注文処理は、注文を扱う 1 つ以上のステージで構成されます。 処理が終わったら、元の注文要求に応答を返します。  
  
 この展開ガイドでは、開発用コンピュータおよび複数の実稼働サーバーにビジネス プロセス管理ソリューションをインストールして実行する方法について説明します。  
  
 ビジネス プロセス管理ソリューションの詳細については、次を参照してください。[ビジネス プロセス管理ソリューションを理解する](../core/understanding-the-business-process-management-solution.md)です。  
  
 **対象読者**  
  
 このドキュメントは、BizTalk Server、Windows Server、および Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に関する知識があることを前提としています。 また、エンタープライズ アプリケーション統合と Web サービスの基本的な概念についても理解していることを前提としています。 さらに、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] を使用してアプリケーションを作成する方法や、プロジェクトの作成、参照の設定、デバッグ モードを使用したソリューションのデバッグおよびテストに関しても理解しておいてください。 IT 担当者および開発者の必要なスキルと知識の詳細については、次を参照してください。[前提条件のスキルと知識](../core/prerequisite-skills-and-knowledge5.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ビジネス プロセス管理ソリューションの開発者のコンピュータ設定](../core/developer-machine-setup-for-the-business-process-management-solution.md)