---
title: 手順 3:Contoso 0 C のパートナーの 2 つの取引先アグリーメントの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, creating
- creating, agreements
- double action tutorial, creating agreements
ms.assetid: b4267faa-5f10-4294-9890-169f1d5ad8f7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 663254f8b0cc6d71508d99d3e7b40e9ac8faef4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281118"
---
# <a name="step-3-creating-the-contoso-0c2-trading-partner-agreement"></a>手順 3:Contoso 0 C のパートナーの 2 つの取引先アグリーメントの作成
Contoso と Fabrikam、Microsoft® を使用して間の取引先パートナー契約を作成するこの手順で[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール。 0c2 の新しい取引先パートナー アグリーメントを作成するプロセス PIP (Partner Interface)。  

### <a name="to-start-the-btarn-management-console"></a>BTARN 管理コンソールを開始するには  

- クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk\<バージョン\>Accelerator for RosettaNet**順にクリックします**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソール。  

### <a name="to-create-the-0c2-trading-partner-agreement"></a>2 取引先パートナー契約の 0 C を作成するには  

1. **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]を右クリックして**契約**、 をクリックして**新規**、 をクリックし、**契約**.  

2. 新しいアグリーメントのプロパティ ダイアログ ボックスで、上、**全般** タブで、次の操作を行います。  


   |         プロパティ          |                        目的                         |
   |---------------------------|-----------------------------------------------------------|
   |         **名前**          |             型**Fabrikam_To_Contoso_0C2**します。             |
   | **プロセスの構成** |    選択**STD_0C2_R01.02**ドロップダウン リストから。     |
   |    **自分の所属組織**    |        選択**Contoso**ドロップダウン リストから。        |
   | **取引先組織**  |       選択**Fabrikam**ドロップダウン リストから。        |
   |     **RNIF のバージョン**      |       選択**V02.00.01**ドロップダウン リストから。       |
   |       **ホーム ロール**       | 選択**Responder (応答)** ドロップダウン リストから。 |
   |         **使用方法**         |         選択**テスト**ドロップダウン リストから。          |


3. をクリックして、**ポート**タブをクリックし、次の操作を行います。  


   |    プロパティ    |                          目的                           |
   |----------------|---------------------------------------------------------------|
   | **アクションの URL** | 型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |
   | **シグナル URL** | 型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |
   |  **同期 URL**  | 型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx** |


4. **[OK]** をクリックします。  

5. 右クリックし、 **Fabrikam_To_Contoso_0C2**アグリーメント、およびクリック**Activate**します。  

## <a name="see-also"></a>参照  
 [手順 4:Contoso 0C4 取引先契約の作成](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-contoso-0c4-trading-partner-agreement.md)