---
title: BtarnConfig | Microsoft Docs
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
ms.openlocfilehash: 50940e57a806f56ae874934052a4c5b7a03a13f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284896"
---
# <a name="btarnconfig"></a>BtarnConfig
BtarnConfig ユーティリティを使用して構成データをインポートまたは、Microsoft® から構成データをエクスポートする[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]環境。 この構成データは、プロセス構成設定、ホーム組織、パートナー、および契約を含む、BTARN 管理コンソールを使用して設定したデータです。  

## <a name="location-in-sdk"></a>SDK でのパス  
 \<*drive*\>\ Program Files (x86)\\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\SDK  

## <a name="running-btarnconfig"></a>Running BtarnConfig  

#### <a name="to-run-btarnconfig"></a>BtarnConfig を実行するには  

1. コマンド プロンプトを開きます。  

2. 移動\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\\します。  

3. コマンド プロンプトで「 **BtarnConfig**と、適切なスイッチを入力し、ENTER キーを押します。  

   > [!NOTE]
   >  次のセクションでは、スイッチについて説明します。  

## <a name="syntax-for-btarnconfig"></a>BtarnConfig の構文  
 このコマンド ライン ツールの起動に使用する構文を次に示します。  

### <a name="syntax-for-importing-configuration-data"></a>構成データをインポートするための構文  

```  
BTARNCONFIG /IMPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  

### <a name="syntax-for-exporting-configuration-data"></a>構成データをエクスポートするための構文  

```  
BTARNCONFIG /EXPORT <filename>.xml [/H] [/P] [/R] [/A]  
```  

### <a name="syntax-description"></a>構文の説明  
 次の表では、BtarnConfig ユーティリティを使用する構文の各部について説明します。  


|       構文       |                                                                                                                          説明                                                                                                                          |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \<*filename*.xml\> | インポートまたはエクスポートするファイルの完全パス。 BTARN のパスを指定しない場合、パスが前提としています\<*ドライブ*\>\ Program Files (x86)\\Microsoft BizTalk\<バージョン\>してのアクセラレータSDK があります。 |
|    **/IMPORT**     |                                                                                          XML データをインポート\< *filename*.xml\> BTARN の構成にします。                                                                                           |
|    **/EXPORT**     |                                                                                             XML データとしての BTARN の構成のエクスポート\< *filename*.xml\>します。                                                                                              |
|       **/H**       |                                                                                                   インポートまたはホーム組織の構成データをエクスポートします。                                                                                                    |
|       **/P**       |                                                                                                        インポートまたはパートナーの構成データをエクスポートします。                                                                                                         |
|       **/R**       |                                                                                                        インポートまたはプロセス構成データをエクスポートします。                                                                                                         |
|       **/A**       |                                                                                                       インポートまたはアグリーメントの構成データをエクスポートします。                                                                                                        |

## <a name="remarks"></a>コメント  
 いずれかを指定しない場合、 **/H**、 **/P**、 **/R**、または **/A**スイッチ、BtarnConfig ユーティリティは、インポートまたはすべてのデータをエクスポートします。 BtarnConfig が次の順序で XML ファイルにデータをエクスポートする 1 つの操作のすべてのデータをエクスポートする場合: ホーム組織、パートナー、プロセス構成、およびアグリーメント。  

 インポートするファイルの構造上の問題がある場合は、BTARN スキーマの検証段階でエラーが検出され、任意のデータをインポートする前に、操作は失敗します。 重複するアイテムをインポートしようとしているなどの別のエラーが発生した場合または HTTPS が必要な PIP/アグリーメントし、インポート操作に失敗します。 ただし、すべてのデータまでにインポートされた構成でポイントが残ります。  

 BizTalk 管理者は、インポートまたは BtarnConfig を使用して構成データをエクスポートする必要があります。 BizTalk 管理者でない場合は、いくつかのインポート操作が失敗するアクセスの問題があるためです。 ただし、同じ BtarnConfig コマンドで他のインポート操作が成功する可能性があります。  

## <a name="see-also"></a>参照  
 [ユーティリティ](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)
