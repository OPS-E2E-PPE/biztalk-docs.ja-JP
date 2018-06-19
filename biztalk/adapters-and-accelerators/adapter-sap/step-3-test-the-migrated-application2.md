---
title: '手順 3: テスト移行 Application2 |Microsoft ドキュメント'
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
ms.openlocfilehash: 6dbf6154337dc9daf5dcfe75b3f5b7299ae843ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216466"
---
# <a name="step-3-test-the-migrated-application"></a>手順 3: 移行後のアプリケーションをテストします。
![手順 3 3](../../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")  
  
 **所要時間:** 5 分  
  
 **目標:** この手順では、WCF ベースを使用してフラット ファイル IDOC を送信することによって移行済みのアプリケーションをテストします[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
## <a name="prerequisites"></a>前提条件  
  
-   BizTalk Server 管理コンソールで物理ポートを BizTalk オーケストレーションの論理ポートにマップして、BizTalk アプリケーションを構成します。  
  
-   WCF ベースの wcf-custom 送信ポートを使用する BizTalk アプリケーションを構成する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。  
  
### <a name="to-test-the-migrated-application"></a>移行したアプリケーションをテストするには  
  
1.  SendIDOC_Migration フォルダーから BOMDOC.txt ファイルをコピーします。 これは、フラット ファイル IDOC を SAP システムに送信します。  
  
2.  貼り付けをファイルにマップされているフォルダーにフラット ファイル IDOC の受信場所。  
  
3.  オーケストレーションがファイルを使用し、IDOC を SAP システムに送信します。 イベント ビューアーにエラーがあるかどうかを確認します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 3: SAP 送信 IDOC の BizTalk プロジェクトを移行します。](../../adapters-and-accelerators/adapter-sap/tutorial-3-migrating-an-sap-send-idoc-biztalk-project.md)