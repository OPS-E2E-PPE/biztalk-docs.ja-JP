---
title: '手順 3: 移行後のアプリケーション 2 のテスト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, testing the migrated application (Send IDOC)
- migration
ms.assetid: 8dc0d127-71ce-4668-a3bf-c893a8f6848d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc49906e58e549a8ed9c90446b011dc3b51e0a45
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017818"
---
# <a name="step-3-test-the-migrated-application"></a>手順 3: 移行後のアプリケーションをテストします。
![ステップ 3/3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、WCF ベースを使用してフラット ファイル IDOC を送信することによって移行済みのアプリケーションをテストします[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="prerequisites"></a>前提条件  
  
- BizTalk アプリケーションを構成するには、BizTalk オーケストレーションの論理ポートを BizTalk Server 管理コンソールで物理ポートにマッピングします。  
  
- WCF ベースの wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
### <a name="to-test-the-migrated-application"></a>移行したアプリケーションをテストするには  
  
1.  SendIDOC_Migration フォルダーから BOMDOC.txt ファイルをコピーします。 これは、SAP システムに送信するフラット ファイル IDOC です。  
  
2.  貼り付け、ファイルにマップされているフォルダーにフラット ファイル IDOC の受信場所。  
  
3.  オーケストレーションは、ファイルを使用し、IDOC を SAP システムに送信します。 イベント ビューアーにエラーがあるかを確認します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: SAP の IDOC 送信 BizTalk プロジェクトを移行する](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)