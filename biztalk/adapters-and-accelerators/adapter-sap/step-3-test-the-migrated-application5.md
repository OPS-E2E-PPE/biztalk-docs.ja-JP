---
title: "手順 3: テスト移行 Application5 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Receive IDOC)
- migration
ms.assetid: 3ad15069-1556-4c0a-8bfd-86704d40c586
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b5e49968e4b0b463b1665d0752689a14039c2da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-migrated-application"></a>手順 3: 移行後のアプリケーションをテストします。
![手順 3 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:**この手順では、WCF ベースを使用してフラット ファイル IDOC を受信して移行したアプリケーションをテストします[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="prerequisites"></a>前提条件  
  
-   BizTalk Server 管理コンソールで物理ポートを BizTalk オーケストレーションの論理ポートにマップして、BizTalk アプリケーションを構成します。  
  
-   BizTalk を構成する Wcf-custom を使用するアプリケーションを受信ポートを WCF ベースの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
### <a name="to-test-the-migrated-application"></a>移行したアプリケーションをテストするには  
  
1.  SAP GUI を起動し、接続 URI で指定した SAP システムに接続します。  
  
2.  SE37 を実行し、外部システムに IDOC を送信する SAP の関数モジュールを起動します。 Wcf-custom 受信ポートの接続 URI で指定されている同じプログラム ID を使用して、IDOC を送信することを確認してください。  
  
3.  オーケストレーションの一部として指定されたファイルの場所で受信 IDOC を探します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: SAP を移行する BizTalk プロジェクトの IDOC を受信](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)