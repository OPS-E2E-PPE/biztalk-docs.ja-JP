---
title: '手順 6: Fabrikam 3A4 取引先を作成するアグリーメントのパートナー |Microsoft Docs'
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
ms.openlocfilehash: a533f00835b8f2200c539baa0e27fbe51ad2c5f6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009547"
---
# <a name="step-6-creating-the-fabrikam-3a4-trading-partner-agreement"></a>手順 6: Fabrikam 3A4 取引先パートナー アグリーメントを作成します。
Contoso と Fabrikam、Microsoft® を使用して間の取引先パートナー契約を作成するこの手順で[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール。 3A4 PIP (Partner Interface Process) のための新しい取引先アグリーメントを作成します。  

### <a name="to-start-the-btarn-management-console"></a>BTARN 管理コンソールを起動するには  

- クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。  

### <a name="to-create-the-3a4-trading-partner-agreement"></a>3A4 取引先アグリーメントを作成するには  

1. **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、右クリックして**契約**、 をポイント**新規**、順にクリックします**アグリーメント**.  

2. **新しいアグリーメントのプロパティ** ダイアログ ボックスの 、**全般** タブで、次の操作を行います。  


   |         プロパティ          |                      目的                       |
   |---------------------------|-------------------------------------------------------|
   |         **名前**          |           型**Fabrikam_To_Contoso_3A4**します。           |
   | **プロセスの構成** |  選択**STD_3A4_V02.02**ドロップダウン リストから。   |
   |    **自分の所属組織**    |     選択**Fabrikam**ドロップダウン リストから。      |
   | **取引先組織**  |      選択**Contoso**ドロップダウン リストから。      |
   |     **RNIF のバージョン**      |     選択**V02.00.01**ドロップダウン リストから。     |
   |       **ホーム ロール**       | 選択**Buyer (開始側)** ドロップダウン リストから。 |
   |         **使用方法**         |       選択**テスト**ドロップダウン リストから。        |


3. **ポート** タブで、次の操作を行います。  


   |    プロパティ    |                          目的                           |
   |----------------|---------------------------------------------------------------|
   | **アクションの URL** | 型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。 |
   | **シグナル URL** | 型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。 |
   |  **同期 URL**  | 型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**します。 |


4. **[OK]** をクリックします。  

5. 右クリックし、 **Fabrikam_To_Contoso_3A4**契約書とクリック**アクティブ化**します。  

## <a name="see-also"></a>参照  
 [手順 7: LOBWebApplication SDK サンプルのビルドと展開](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)