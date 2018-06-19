---
title: スキーマ生成ウィザードを拡張する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 11db44e07191b0996043dd6b819ef2ba9162a0e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254018"
---
# <a name="how-to-extend-the-schema-generator-wizard"></a>スキーマ生成ウィザードを拡張する方法
既存のスキーマ生成ウィザードを拡張する方法とスキーマの生成用の新規作成ウィザードを作成する方法。  
  
## <a name="extend-the-existing-schema-wizard"></a>既存のスキーマ ウィザードを拡張します。  
  
1.  既存のスキーマ生成ウィザードに統合できる新しいスキーマ生成モジュールを作成する ISchemaGenerator インターフェイスを実装します。  
  
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
  
2.  次の Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インストール フォルダーに、結果として得られるアセンブリをドロップします。  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema エディター拡張機能  
  
     次にスキーマ生成ウィザードを実行すると、新しいスキーマ生成モジュールが自動的に選択されます。  
  
 新しいスキーマ ウィザードを作成するには、次の手順を実行します。  
  
 **SDK 内の場所**  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\Utilities\Schema generator  
  
### <a name="create-a-new-schema-wizard"></a>新しいスキーマ ウィザードを作成します。  
  
1.  InstallDTD.vbs をして Microsoft.BizTalk.DTDToXSDGenerator.dll をインストールする実行[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema エディター拡張機能です。 DTDToXSDGenerator.dll は、DTD ファイルを XSD に変換するために使用できるクラスを公開します。  
  
2.  InstallWFX.vbs を Microsoft.BizTalk.WFXToXSDGenerator.dll のインストールを実行して[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema エディター拡張機能です。 WFXToXSDGenerator.dll は、WFX ファイルを XSD に変換するために使用できるクラスを公開します。  
  
## <a name="see-also"></a>参照  
 [SDK のユーティリティ](../core/utilities-in-the-sdk.md)