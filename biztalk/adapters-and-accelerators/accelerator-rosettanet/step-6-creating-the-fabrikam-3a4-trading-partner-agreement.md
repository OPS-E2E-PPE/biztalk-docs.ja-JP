---
title: '手順 6: Fabrikam 3A4 取引を作成するパートナーの契約 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: 6ccd2414-a1d4-460e-9529-65b2d30cfca6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 802d3648d0f7709fdfbed70c3e29a4abc565a51c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965832"
---
# <a name="step-6-creating-the-fabrikam-3a4-trading-partner-agreement"></a>手順 6: Fabrikam 3A4 取引先アグリーメントの作成
ここでは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理コンソールを使用して、Contoso と Fabrikam の間の取引先アグリーメントを作成します。 3A4 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。  
  
### <a name="to-start-the-btarn-management-console"></a>BTARN 管理コンソールを起動するには  
  
-   をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**をクリックして**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールです。  
  
### <a name="to-create-the-3a4-trading-partner-agreement"></a>3A4 取引先アグリーメントを作成するには  
  
1.   **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**契約**、 をポイント**新規**、クリックして**アグリーメント**.  
  
2.  **新しいアグリーメントのプロパティ** ダイアログ ボックスで、**全般** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**名前**|型**Fabrikam_To_Contoso_3A4**です。|  
    |**プロセスの構成**|選択**STD_3A4_V02.02**ドロップダウン リストからです。|  
    |**自分の所属組織**|選択**Fabrikam**ドロップダウン リストからです。|  
    |**パートナー組織**|選択**Contoso**ドロップダウン リストからです。|  
    |**RNIF のバージョン**|選択 **[v02.00.01]** ドロップダウン リストからです。|  
    |**ホーム ロール**|選択**Buyer (開始側)** ドロップダウン リストからです。|  
    |**使用方法**|選択**テスト**ドロップダウン リストからです。|  
  
3.  **ポート** タブで、次の操作します。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**アクションの URL**|型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。|  
    |**シグナル URL**|型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。|  
    |**同期 URL**|型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**です。|  
  
4.  **[OK]** をクリックします。  
  
5.  右クリックし、 **Fabrikam_To_Contoso_3A4**アグリーメントをクリックして**Activate**です。  
  
## <a name="see-also"></a>参照  
 [手順 7: LOBWebApplication SDK サンプルのビルドと展開](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)