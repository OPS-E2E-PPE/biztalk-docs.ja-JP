---
title: 手順 4:取引アグリーメントの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trade agreeements
- loopback tutorial, creating trade agreements
- agreements, creating
ms.assetid: 9bcb80b1-fefc-4f1c-ae03-fb736cdfd524
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aa9be8b5435b212838a40059e784b0f54c17b36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280991"
---
# <a name="step-4-create-a-trade-agreement"></a>手順 4:取引アグリーメントを作成します。
この手順で、Microsoft® を使用してホームとパートナーの組織間の取引アグリーメントを作成する[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理コンソール。  

### <a name="to-create-a-trade-agreement"></a>取引先アグリーメントを作成するには  

1. **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理コンソールで、展開**BizTalk\<バージョン\>Accelerator for RosettaNet**、右クリックして**契約**、 をクリックして**新規**、 をクリックし、**契約**します。  

2. **新しいアグリーメントのプロパティ** ダイアログ ボックスの 、**全般** タブで、次の操作を行います。  


   |         プロパティ          |                     目的                     |
   |---------------------------|----------------------------------------------------|
   |         **名前**          |             型**売買契約**します。              |
   | **プロセスの構成** | 選択**STD_0C1_R01.02**ドロップダウン リストから。 |
   |    **自分の所属組織**    |      選択**ホーム**ドロップダウン リストから。      |
   | **取引先組織**  |    選択**パートナー**ドロップダウン リストから。     |
   |       **ホーム ロール**       |   選択**イニシエーター**ドロップダウン リストから。    |


3. **新しいアグリーメントのプロパティ** ダイアログ ボックスの 、**ポート** タブで、次の操作を行います。  


   |    プロパティ    |                                         目的                                         |
   |----------------|--------------------------------------------------------------------------------------------|
   | **アクションの URL** |                   型 **<http://localhost/BTARNApp/RNIFReceive.aspx>** します。                   |
   | **シグナル URL** |                   型 **<http://localhost/BTARNApp/RNIFReceive.aspx>** します。                   |
   |  **同期 URL**  | 空白のままにします。 同期 URL が必要なため、同期プロセス PIP (Partner Interface) ではありません。 |


4. クリックして**適用**、順にクリックします**OK**します。  

   取引先アグリーメントを作成した後は、アクティブ化する必要があります。  

### <a name="to-activate-the-trade-agreement"></a>取引先アグリーメントをアクティブ化するには  

- [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリックして**契約**を右クリックして**取引先アグリーメント**で結果ウィンドウをクリック**Activate**.  

## <a name="see-also"></a>参照  
 [手順 5:ミラー アグリーメントの作成](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)