---
title: アダプター構成のカスタム ドロップダウン エディター |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a1b0961-652f-42b8-a18a-17abe9542cdd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcf59a1692b8921d7e73799dcabafa4ad467f7c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389822"
---
# <a name="custom-drop-down-editor-for-adapter-configuration"></a>アダプター構成のカスタム ドロップダウン エディター
カスタム エディターのコードから派生したエディターを示しています、 **System.Drawing.Design.UITypeEditor**パスワードを入力するためのドロップダウン テキスト ボックスを表示するクラス。 **GetEditStyle**のオーバーライド**UIEditorEditStyle.DropDown**をドロップダウン サブコントロールを示すためにします。 サービス メソッドは、 **DropDownControl**と**CloseDropDown**で作成されたコントロールを管理**CreatePassword**します。  
  
 次のコードでは、カスタム ドロップダウン エディターのクラス定義を示します。  
  
```  
/*************************************************************************  
 * Copyright (c) 1999-2004 Microsoft Corporation. All rights reserved.   *  
 *                                                                       *  
 * THIS CODE AND INFORMATION IS PROVIDED "AS IS" WITHOUT WARRANTY OF ANY *  
 * KIND, WHETHER EXPRESSED OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE  *  
 * IMPLIED WARRANTIES OF MERCHANTABILITY AND/OR FITNESS FOR A PARTICULAR *  
 * PURPOSE. THE ENTIRE RISK OF USE OR RESULTS IN CONNECTION WITH THE USE *  
 * OF THIS CODE AND INFORMATION REMAINS WITH THE USER.                   *  
 *************************************************************************/  
  
using System;  
using System.ComponentModel;  
using System.Drawing.Design;  
using System.Windows.Forms;  
using System.Windows.Forms.Design;  
using System.Security;  
using System.Security.Permissions;  
using Microsoft.BizTalk.Adapter.Framework;  
using Microsoft.BizTalk.Adapter.Framework.Forms;  
  
namespace AdapterManagement.ComponentModel {  
   /// <summary>  
   /// PasswordUITypeEditor implements a user interface for acquiring passwords  
   /// within a visual designer.  
   /// </summary>  
   public class PasswordUITypeEditor : UITypeEditor {  
      public const char PasswordChar = '\u25cf';  
      private IWindowsFormsEditorService _service = null;  
      private TextBox _password = null;  
  
      [SecurityPermissionAttribute(SecurityAction.LinkDemand)]  
      public override UITypeEditorEditStyle GetEditStyle(ITypeDescriptorContext context) {  
         if (null != context && null != context.Instance) {  
            return UITypeEditorEditStyle.DropDown;  
         }  
         return base.GetEditStyle(context);  
      }  
  
      [SecurityPermissionAttribute(SecurityAction.LinkDemand)]  
      public override object EditValue(ITypeDescriptorContext context,   
                               IServiceProvider provider,  
                               object value) {  
         if (null != context && null != context.Instance && null != provider) {  
            this._service = (IWindowsFormsEditorService) provider.GetService   
                        (typeof(IWindowsFormsEditorService));  
            if (null != this._service) {  
               this._password = CreatePassword();  
               this._service.DropDownControl(this._password);  
               value = this._password.Text;  
            }  
         }  
         return value;  
      }  
  
      private TextBox CreatePassword () {  
         TextBox password = new TextBox();  
         password.PasswordChar = PasswordUITypeEditor.PasswordChar;  
         password.Leave += new EventHandler(password_Leave);  
      }  
  
      private void password_Leave(object sender, EventArgs e) {  
         if (null != this._service) {  
            this._service.CloseDropDown();  
         }  
      }  
   } // PasswordUITypeEditor  
} // Microsoft.BizTalk.Adapter.Framework.ComponentModel  
```  
  
## <a name="see-also"></a>参照  
 [カスタム アダプター構成デザイナー](../core/custom-adapter-configuration-designer.md)   
 [アダプター構成のカスタム モデル ダイアログ エディター](../core/custom-modal-dialog-editor-for-adapter-configuration.md)   
 [アダプターの構成のカスタム型コンバーター](../core/custom-type-converter-for-adapter-configuration.md)   
 [アダプターの詳細構成コンポーネント](../core/advanced-configuration-components-for-adapters.md)