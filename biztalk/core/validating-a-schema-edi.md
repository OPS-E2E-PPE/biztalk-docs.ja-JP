---
title: スキーマの検証 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6175460-2dcf-4fef-b770-02f0a058bf93
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12f54b77420a9e03e701c5e154bba681b46c166c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997515"
---
# <a name="validating-a-schema-edi"></a>スキーマの検証 (EDI)
デザイン時に EDI スキーマを検証できます。 それには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の XML ツール拡張を使用します。 スキーマの検証操作では、EDI ルールに基づいてスキーマの検証が行われます。 スキーマを検証するために入力メッセージ インスタンスを指定する必要はありません。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-validate-a-schema"></a>スキーマを検証するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。 ソリューション エクスプローラーで、検証するメッセージ スキーマをプロジェクトに追加します。  
  
   > [!NOTE]
   >  メッセージ スキーマは [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI folder フォルダーの下の該当するサブフォルダーにあります。 スキーマ ファイルをインストールする方法の詳細については、次を参照してください。 [EDI スキーマ ファイルをインストールする方法](http://msdn.microsoft.com/library/787f45d9-d95d-40f4-a4ac-0a0e711f7550)します。  
   > 
   > [!NOTE]
   >  スキーマを検証するためにプロジェクトをビルドする必要はありません。  
  
2. ソリューション エクスプ ローラーでスキーマを右クリックし、をクリックし、**スキーマの検証**です。  
  
3. 操作が成功したことを示すメッセージが [出力] ウィンドウに表示されていることを確認します。  
  
## <a name="see-also"></a>参照  
 [デザイン時 XML ツールを使用します。](../core/using-design-time-xml-tools.md)