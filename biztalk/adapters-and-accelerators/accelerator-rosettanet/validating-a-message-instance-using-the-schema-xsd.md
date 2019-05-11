---
title: スキーマ XSD を使用してメッセージ インスタンスの検証 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schema XSD
- validating, messages
- messages, validating
- schemas, XSDs
ms.assetid: c4cbf6b4-130d-4e0f-840b-c8008fafac0b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3c8c234ecdb79b8aa2e15c99717396199514e29
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299948"
---
# <a name="validating-a-message-instance-using-the-schema-xsd"></a>スキーマ XSD を使用してメッセージ インスタンスの検証
このトピックでは、その Microsoft® スキーマ XSD ファイルのいずれかを使用してメッセージ インスタンスを検証する方法を説明します[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]Rnpip アセンブリ ファイルに組み込まれています。  
  
### <a name="to-validate-a-message-instance-using-the-schema-xsd"></a>スキーマ XSD を使用してメッセージ インスタンスを検証するには  
  
1.  開始**Microsoft Visual Studio 2012**します。  
  
2.  **ファイル**、 をポイント**オープン**、 をクリックし、**プロジェクト**します。  
  
3.  検索*\<ドライブ\>* \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemas、 をクリックして**RNPIPs.btproj**、クリックして**オープン**します。  
  
4.  ソリューション エクスプ ローラーで、 **Rnpip**をクリックして、メッセージ インスタンスの検証に使用する XSD スキーマを右クリックして**プロパティ**します。  
  
5.  [プロパティ ページ] ダイアログ ボックスで、**入力インスタンス ファイル名**、ファイルが含まれているフォルダーに移動、メッセージ インスタンス XML ファイルを選択およびクリックして**オープン**します。  
  
6.  **[OK]** をクリックします。  
  
7.  ソリューション エクスプ ローラーで、クリックして、メッセージ インスタンスの検証に使用する XSD スキーマを右クリックして**インスタンスの検証**です。  
  
## <a name="see-also"></a>参照  
 [Rnpip の既存の PIP の変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)   
 [PIP の操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)