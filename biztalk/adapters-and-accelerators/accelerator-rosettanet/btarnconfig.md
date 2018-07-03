---
title: BtarnConfig |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, exporting configuration data
- BTARN, BtarnConfig utility
- BtarnConfig utility
- BTARN, importing configuration data
ms.assetid: 8c95be2a-7df5-47fb-ae2d-64fa27e2811a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 542ed5729ce4f5ed7ca4a6d453b3169bb1f43d01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991467"
---
# <a name="btarnconfig"></a>BtarnConfig
BtarnConfig ユーティリティを使用して構成データをインポートまたは、Microsoft® から構成データをエクスポートする[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]環境。 この構成データは、BTARN 管理コンソールを使用して設定するデータで、プロセス構成設定、ホーム組織、パートナー、アグリーメントなどが含まれます。  

## <a name="location-in-sdk"></a>SDK でのパス  
 \<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk  

## <a name="running-btarnconfig"></a>BtarnConfig の実行  

#### <a name="to-run-btarnconfig"></a>BtarnConfig を実行するには  

1. コマンド プロンプトを開きます。  

2. 移動\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。  

3. コマンド プロンプトで「 **BtarnConfig**と、適切なスイッチを入力し、ENTER キーを押します。  

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


|       構文       |                                                                                                                          説明                                                                                                                          |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<*ファイル名*.xml\> | インポートまたはエクスポートするファイルのフルパス。 BTARN のパスを指定しない場合、パスが前提としています\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>してのアクセラレータSDK があります。 |
|    **/インポート**     |                                                                                          XML データをインポート\< *filename*.xml\> BTARN の構成にします。                                                                                           |
|    **/EXPORT**     |                                                                                             XML データとしての BTARN の構成のエクスポート\< *filename*.xml\>します。                                                                                              |
|       **/H**       |                                                                                                   ホーム組織の構成データをインポートまたはエクスポートします。                                                                                                    |
|       **/P**       |                                                                                                        取引先の構成データをインポートまたはエクスポートします。                                                                                                         |
|       **/R**       |                                                                                                        プロセス構成データをインポートまたはエクスポートします。                                                                                                         |
|       **/A**       |                                                                                                       アグリーメントの構成データをインポートまたはエクスポートします。                                                                                                        |

## <a name="remarks"></a>コメント  
 いずれかを指定しない場合、 **/H**、 **/P**、 **/R**、または **/A**スイッチ、BtarnConfig ユーティリティは、インポートまたはすべてのデータをエクスポートします。 一度の操作で全データをエクスポートする場合は、ホーム組織、取引先、プロセス構成、アグリーメントの順にデータが XML にエクスポートされます。  

 インポート元のファイルに構造上の問題がある場合は、スキーマ検証ステージでエラーが検出され、データがインポートされる前に操作に失敗します。 別のエラーが発生した場合、たとえば重複項目をインポートしようとしている場合や、PIP/アグリーメントに HTTPS が必要な場合は、インポート操作に失敗します。 ただし、その時点までにインポートされたデータは構成に残ります。  

 BtarnConfig を使用して構成データをインポートまたはエクスポートするには、BizTalk 管理者でなければなりません。 BizTalk 管理者でない場合は、アクセス権の問題でインポート操作に失敗する可能性がありますが、 BtarnConfig コマンドを使用した他のインポート操作には成功する場合もあります。  

## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
