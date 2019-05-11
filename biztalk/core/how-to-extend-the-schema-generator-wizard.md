---
title: スキーマ生成ウィザードを拡張する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- utilities, Schema Generator Wizard
- Schema Generator Wizard
ms.assetid: ea4b5532-f904-4da0-9612-e092e7e4edc1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac920751fc8f653433525150be5684f93d2eb2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337723"
---
# <a name="how-to-extend-the-schema-generator-wizard"></a>スキーマ生成ウィザードを拡張する方法
スキーマの生成用の新規作成ウィザードを作成する方法と、既存のスキーマ生成ウィザードを拡張する方法。  
  
## <a name="extend-the-existing-schema-wizard"></a>既存のスキーマ ウィザードを拡張します。  
  
1. 既存のスキーマ生成ウィザードに統合できる新しいスキーマ生成モジュールを作成する ISchemaGenerator インターフェイスを実装します。  
  
   ```  
   public interface ISchemaGenerator  
   {  
   //Method to extract a schema from a document.  
   void GenerateSchema(string inputDocument,string outputDocumentPath);  
  
   //Method to extract the errors.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] Errors();  
  
   //Method to extract the warnings.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] Warnings();  
  
   //Method to extract the referenced schemas.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] ReferencedSchemas();  
   }  
   ```  
  
2. 次の Microsoft では、生成されたアセンブリをドロップ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストール フォルダー。  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema Editor Extensions  
  
    次に、スキーマ生成ウィザードを実行したときは自動的に選択、新しいスキーマ生成モジュール。  
  
   新しいスキーマ ウィザードを作成するのにには、次の手順を使用します。  
  
   **SDK の場所**  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\Utilities\Schema Generator  
  
### <a name="create-a-new-schema-wizard"></a>新しいスキーマ ウィザードを作成します。  
  
1. InstallDTD.vbs を Microsoft.BizTalk.DTDToXSDGenerator.dll のインストールを実行して[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema エディター拡張機能。 DTDToXSDGenerator.dll は、DTD ファイルを XSD に変換するのに使用できるクラスを公開します。  
  
2. InstallWFX.vbs を Microsoft.BizTalk.WFXToXSDGenerator.dll のインストールを実行して[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema エディター拡張機能。 WFXToXSDGenerator.dll は、WFX ファイルを XSD に変換するのに使用できるクラスを公開します。  
  
## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)