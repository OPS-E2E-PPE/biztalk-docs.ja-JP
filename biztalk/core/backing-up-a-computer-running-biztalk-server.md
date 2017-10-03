---
title: "BizTalk Server を実行しているコンピューターのバックアップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70f53b41-8083-4b56-8698-e75a13b21a69
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 537ea40b39ecd35127b62f8d96f0175e98a1f3b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="backing-up-a-computer-running-biztalk-server"></a>BizTalk Server を実行しているコンピュータのバックアップ
BizTalk Server を実行しているコンピュータで復旧不可能なハードウェア障害が発生した場合、同等のコンピュータに置き換える必要があります。 基本プラットフォーム、必要なソフトウェア、BizTalk Server コンポーネント、および同等の構成設定が備わった代替コンピュータをセットアップします。 これらの構成設定は、BizTalk アプリケーションを正しく機能させるために必要な、適切なレジストリ エントリ、ファイル、フォルダ、および関連する Windows サービスで構成される場合があります。  
  
 BizTalk Server データベースをバックアップするほか、次の BizTalk Server コンポーネントをバックアップして、ハードウェア障害が発生した後 BizTalk Server を復旧できるようにしておく必要があります。  
  
-   BizTalk Server 構成  
  
-   エンタープライズ シングル サインオン (SSO) マスタ シークレット  
  
-   ビジネス アクティビティ監視 (BAM) ポータル (BAM を使用している場合のみ必要)  
  
-   BizTalk アプリケーション  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server の構成をバックアップする方法](../core/how-to-back-up-the-biztalk-server-configuration.md)  
  
-   [マスター シークレットをバックアップする方法](../core/how-to-back-up-the-master-secret.md)  
  
-   [BAM ポータルをバックアップする方法](../core/how-to-back-up-the-bam-portal.md)  
  
-   [BizTalk Server アプリケーションをバックアップします。](../core/backing-up-biztalk-server-applications.md)