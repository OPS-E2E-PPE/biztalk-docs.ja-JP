---
title: 手順 3:テスト移行 Application5 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Receive IDOC)
- migration
ms.assetid: 3ad15069-1556-4c0a-8bfd-86704d40c586
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8754056eeb173fc86201a108e95605074101dea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372801"
---
# <a name="step-3-test-the-migrated-application"></a>手順 3:移行したアプリケーションをテストします。
![ステップ 3/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、WCF ベースを使用してフラット ファイル IDOC を受信することによって、移行済みのアプリケーションをテストします[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
  
- BizTalk アプリケーションを構成するには、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマッピングします。  
  
- 構成、BizTalk WCF カスタムを使用するアプリケーションが WCF ベースのポートを受信[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
### <a name="to-test-the-migrated-application"></a>移行したアプリケーションをテストするには  
  
1.  SAP の GUI を起動し、接続 URI で指定した SAP システムに接続します。  
  
2.  SE37 を実行して、sap の IDOC を外部システムに送信する関数モジュールを呼び出します。 Wcf-custom の受信ポートの接続 URI で指定されている同じプログラム ID を使用して IDOC を送信することを確認します。  
  
3.  オーケストレーションの一部として指定されたファイルの場所で受信 IDOC を探します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 4: SAP の IDOC 受信 BizTalk プロジェクトを移行する](../../adapters-and-accelerators/adapter-sap/tutorial-4-migrating-an-sap-receive-idoc-biztalk-project.md)