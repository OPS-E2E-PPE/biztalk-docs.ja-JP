---
title: スキーマ XSD を使用してメッセージ インスタンスの検証 |Microsoft ドキュメント
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
ms.openlocfilehash: 0eda0b76b3daff53290264169c5b2effe80a9e5c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963968"
---
# <a name="validating-a-message-instance-using-the-schema-xsd"></a>スキーマ XSD を使用してメッセージ インスタンスの検証
ここでは、Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] によって RNPIP アセンブリ ファイルに構築したスキーマ XSD ファイルを使用してメッセージ インスタンスを検証する方法を説明します。  
  
### <a name="to-validate-a-message-instance-using-the-schema-xsd"></a>スキーマ XSD を使用してメッセージ インスタンスを検証するには  
  
1.  開始**Microsoft Visual Studio 2012**です。  
  
2.  **ファイル**、 をポイント**開く**、クリックして**プロジェクト**です。  
  
3.  検索*\<ドライブ\>* \Program Files\Microsoft BizTalk\<バージョン\>Accelerator for rosettanet \sdk\schemas をクリックして**RNPIPs.btproj**、クリックして**開く**です。  
  
4.  ソリューション エクスプ ローラーで、 **Rnpip**、クリックして、メッセージ インスタンスの検証に使用する XSD スキーマを右クリックして**プロパティ**です。  
  
5.  [プロパティ ページ] ダイアログ ボックスで、**入力インスタンス ファイル名**、ファイルが含まれているフォルダーを探し、メッセージ インスタンス XML ファイルを選択およびクリックして**開く**です。  
  
6.  **[OK]** をクリックします。  
  
7.  ソリューション エクスプ ローラーでスキーマを右クリックして、クリックして、メッセージ インスタンスの検証に使用する XSD**インスタンスの検証**です。  
  
## <a name="see-also"></a>参照  
 [Rnpip の既存の PIP の変更](../../adapters-and-accelerators/accelerator-rosettanet/modifying-an-existing-pip-in-rnpips.md)   
 [PIP の操作](../../adapters-and-accelerators/accelerator-rosettanet/working-with-pips.md)