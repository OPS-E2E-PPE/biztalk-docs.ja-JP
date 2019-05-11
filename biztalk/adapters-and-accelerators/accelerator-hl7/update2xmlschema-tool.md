---
title: Update2XMLSchema ツール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML schemas, Update2XMLSchema tool
- schemas, Update2XMLSchema tool
- Update2XMLSchema tool
- Update2XMLSchema tool, syntax
ms.assetid: fd861e2f-ebda-427f-bd52-a2f05b7e22da
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b47b3cc13d5c77dcc8efc8f5fd19e049b321a4f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286468"
---
# <a name="update2xmlschema-tool"></a>Update2XMLSchema ツール
Update2XMLSchema ツールでは、BizTalk エディターを操作する HL7 2. XML スキーマを変更することができます。 これは、Microsoft 内で特定の HL7 2. XML スキーマが正しく機能しないため[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]変更なし。 スキーマを変更した後、ツールに置きます Schemas フォルダーで、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]がインストールされている、たとえば、 *\<ドライブ\>*: \Program Files\Microsoft BizTalk \<のバージョン\>HL7\Templates\Schemas のアクセラレータです。  
  
 Update2XMLSchema ツールの実行結果のスキーマの一部のフィールドに手動で更新する必要があります。 参照してください[手動更新のために必要な](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)それらのスキーマの一覧についてはします。  
  
## <a name="syntax"></a>構文  
 このツールにある*\<ドライブ\>*: \Program Files\Microsoft BizTalk\<バージョン\>HL7\SDK\2XML ユーティリティのアクセラレータです。 次のコマンドでコマンド プロンプトでは、このツールを実行します。  
  
```  
Update2XMLSchema /s /v  
```  
  
 次の表は、このコマンドで使用するパラメーターを一覧表示します。  
  
|パラメーター|名前|値|  
|---------------|----------|-----------|  
|*S*|ソース|元の HL7 スキーマの完全なパス|  
|*V*|バージョン|2. XML スキーマのバージョン: 2.3.1、2.4、または 2.5|  
  
## <a name="example"></a>例  
  
-   C:\231XML\v231\xsd ディレクトリにある version 2.3.1 2. XML スキーマを変更するは、コマンド プロンプトで次のコマンドを入力します。  
  
```  
Update2XMLSchema /s c:\231XML\v231\xsd /v 2.3.1  
```  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [必要な手動更新](../../adapters-and-accelerators/accelerator-hl7/required-manual-updates.md)