---
title: BizTalk Server を実行しているコンピューターのバックアップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 70f53b41-8083-4b56-8698-e75a13b21a69
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04f8a0073ffd4117da1d5cf5d92dd969b9a0abfc
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528573"
---
# <a name="backing-up-a-computer-running-biztalk-server"></a>BizTalk Server を実行しているコンピューターのバックアップ
BizTalk Server を実行しているコンピューターに、回復不可能なハードウェア障害が低下した場合は、同一の 1 つでそのコンピューターを置き換える必要があります。 基本プラットフォームのソフトウェア、ソフトウェアの前提条件、BizTalk Server コンポーネント、および同等の構成設定で、代替コンピューターを設定する必要があります。 これらの構成設定は、適切なレジストリ エントリ、ファイル、フォルダー、および BizTalk アプリケーションの適切な操作に必要な関連する Windows サービスで構成されます。  
  
 BizTalk Server データベースをバックアップするだけでなくは、ハードウェア障害の後、BizTalk Server を回復できることを確認するのには、次の BizTalk Server コンポーネントをバックアップする必要があります。  
  
-   BizTalk Server の構成  
  
-   エンタープライズ シングル サインオン (SSO) マスター シークレット  
  
-   (BAM を使用している場合を除きは必要ありません)、ビジネス アクティビティ監視 (BAM) ポータル  
  
-   BizTalk アプリケーション  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server の構成をバックアップする方法](../core/how-to-back-up-the-biztalk-server-configuration.md)  
  
-   [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)  
  
-   [BAM ポータルをバックアップする方法](../core/how-to-back-up-the-bam-portal.md)  
  
-   [BizTalk Server アプリケーションのバックアップ](../core/backing-up-biztalk-server-applications.md)