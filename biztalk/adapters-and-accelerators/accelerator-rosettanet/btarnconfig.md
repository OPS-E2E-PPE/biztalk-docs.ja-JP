---
title: "BtarnConfig |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BTARN, exporting configuration data
- BTARN, BtarnConfig utility
- BtarnConfig utility
- BTARN, importing configuration data
ms.assetid: 8c95be2a-7df5-47fb-ae2d-64fa27e2811a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78ab62a86e97bf70e07629052a850b5aea2cee27
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="btarnconfig"></a>BtarnConfig
BtarnConfig ユーティリティは、[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 環境との間で構成データをインポートまたはエクスポートする場合に使用します。 この構成データは、BTARN 管理コンソールを使用して設定するデータで、プロセス構成設定、ホーム組織、パートナー、アグリーメントなどが含まれます。  
  
## <a name="location-in-sdk"></a>SDK でのパス  
 \<*ドライブ*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk  
  
## <a name="running-btarnconfig"></a>BtarnConfig の実行  
  
#### <a name="to-run-btarnconfig"></a>BtarnConfig を実行するには  
  
1.  コマンド プロンプトを開きます。  
  
2.  移動\<*ドライブ*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\です。  
  
3.  コマンド プロンプトで次のように入力します。 **BtarnConfig**、適切なスイッチを入力して、ENTER キーを押します。  
  
    > [!NOTE]
    >  スイッチについては次のセクションで説明します。  
  
## <a name="syntax-for-btarnconfig"></a>BtarnConfig の構文  
 以下に、このコマンドライン ツールを起動するための構文を示します。  
  
### <a name="syntax-for-importing-configuration-data"></a>構成データをインポートするための構文  
  
```  
BTARNCONFIG /IMPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  
  
### <a name="syntax-for-exporting-configuration-data"></a>構成データをエクスポートするための構文  
  
```  
BTARNCONFIG /EXPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  
  
### <a name="syntax-description"></a>構文の説明  
 次の表で、BtarnConfig が使用する構文の各部について説明します。  
  
|構文|Description|  
|------------|-----------------|  
|\<*filename*.xml\>|インポートまたはエクスポートするファイルのフルパス。 BTARN が想定パスは、パスを指定しない場合\<*ドライブ*\>\ Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<バージョン\>Accelerator for RosettaNet\SDK です。|  
|**/インポート**|XML データをインポート\< *filename*.xml\> BTARN の構成にします。|  
|**/エクスポート**|XML データとしての BTARN の構成のエクスポート\< *filename*.xml\>です。|  
|**/H**|ホーム組織の構成データをインポートまたはエクスポートします。|  
|**/P**|取引先の構成データをインポートまたはエクスポートします。|  
|**/R**|プロセス構成データをインポートまたはエクスポートします。|  
|**/A**|アグリーメントの構成データをインポートまたはエクスポートします。|  
  
## <a name="remarks"></a>解説  
 いずれかを指定しない場合、 **/H**、 **/P**、 **/R**、または**/A**スイッチ、BtarnConfig ユーティリティをインポートまたはすべてのデータをエクスポートします。 一度の操作で全データをエクスポートする場合は、ホーム組織、取引先、プロセス構成、アグリーメントの順にデータが XML にエクスポートされます。  
  
 インポート元のファイルに構造上の問題がある場合は、スキーマ検証ステージでエラーが検出され、データがインポートされる前に操作に失敗します。 別のエラーが発生した場合、たとえば重複項目をインポートしようとしている場合や、PIP/アグリーメントに HTTPS が必要な場合は、インポート操作に失敗します。 ただし、その時点までにインポートされたデータは構成に残ります。  
  
 BtarnConfig を使用して構成データをインポートまたはエクスポートするには、BizTalk 管理者でなければなりません。 BizTalk 管理者でない場合は、アクセス権の問題でインポート操作に失敗する可能性がありますが、 BtarnConfig コマンドを使用した他のインポート操作には成功する場合もあります。  
  
## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)